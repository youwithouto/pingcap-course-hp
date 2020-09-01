# Homework | Week 03

## 00 | Issue

[Issue 19644](https://github.com/pingcap/tidb/issues/19644)

## 01 | 目的

- 分析 TiDB 的可能性能瓶颈
  - 部署 TiDB 集群
  - 使用性能测试工具对 TiDB 集群进行性能测试
  - 将可能的性能问题整理为 GitHub Issue

## 02 | 思路

本次作业是对 Week 02 的延伸。测试部分除了可以使用本周增加的工具外，基本与 Week 02 相同。

## 03 | Issues

### 测试环境

- 云平台：Google Cloud
- 虚拟主机类型（使用不同机型进行了两次测试）：
  - `n1-standard-8`
    - vCPU 数：**8**
    - 内存：**30GB**
  - `e2-standard-2`
    - vCPU 数：**2**
    - 内存：**8GB**
- 操作系统：`ubuntu-1804-lts` (NVMe-optimised)

### 集群主机架构

本次作业共使用 8 台虚拟主机：

- `cluster-controller`
  - 部署 `tiup`
  - 本次作业中所有测试均在此台主机上进行
- `tidb-0`，`tidb-1`，`tidb-2`
  - 部署 TiDB 和 PD
- `tikv-0`，`tikv-1`，`tikv-2`
  - 挂载 SSD
  - 部署 TiKV
- `cluster-monitor`
  - 部署 Monitoring Server，Grafana，Alert Manager

### 分析

对于一个 TiDB 集群，不同的输入对应着不同的压力，最直接的例子就是 tpc-h 测试。

当 tpc-h 测试进行时，TiDB 集群会接收到不同的查询请求，并且涉及多表联合。此时不同的查询产生的瓶颈出现在了不同的位置，例如：[TiDB profiling - 01](./static/profiling/profiling_2_2_tidb_10_240_0_10_4000580655635.svg) 和 [TiDBprofiling - 02](./static/profiling/profiling_5_5_tidb_10_240_0_10_4000322961580.svg) 是在 tpc-h 正在做不同类型的测试时对 TiDB 进行的采样，各个函数的耗时在请求处理前期基本一致，但是由中期开始，函数耗时变得完全不同，分枝点为 `(*ListInDisk) GetRow`。在该分枝点之后，TiDB 主要处理 结果集（ResultSet），并且绝大多数被调用的函数为 Golang Runtime 函数，其中占用时长较多的是与 内存分配（malloc）和 回收（Garbage Collection）相关的代码。

以下这条请求占用约 2GB 内存，耗时约 30s，是典型的耗费时间和空间的查询。原因应该是该请求中的嵌套查询所致。外层查询依赖于内层查询的结果，即外层查询必须将内层查询的结果完整地载入内存才可以开始进行（需要查看源码，验证嵌套查询是否有经过下推处理）。

```sql
SELECT
  nation,
  o_year,
  sum (amount) AS sum_profit
FROM
  (
    SELECT
      n_name AS nation,
      extract (
        year
        FROM
          o_orderdate
      ) AS o_year,
      l_extendedprice * (? - l_discount) - ps_supplycost * l_quantity AS amount
    FROM
      part,
      supplier,
      lineitem,
      partsupp,
      orders,
      nation
    WHERE
      s_suppkey = l_suppkey
      AND ps_suppkey = l_suppkey
      AND ps_partkey = l_partkey
      AND p_partkey = l_partkey
      AND o_orderkey = l_orderkey
      AND s_nationkey = n_nationkey
      AND p_name LIKE ?
  ) AS profit
GROUP BY
  nation,
  o_year
ORDER BY
  nation,
  o_year DESC;
```

![大内存查询](static/sql/Screen%20Shot%202020-08-24%20at%207.18.27%20am.png)

由于 TiDB 将计算下推到 TiKV，当 TiDB 接收到多个 TiKV 实例的多个结果集时，TiDB 有可能需要做大内存的计算，所以 TiDB 对 TiKV 返回结果的处理可能是性能瓶颈之一，更改 `tidb_distsql_scan_concurrency` 有可能会对该问题有所缓解；有时这种瓶颈可能为 Golang Runtime 对内存的优化不够。相应代码均在 Executor 模块下。

---

![Execution Plan](static/sql/Screen%20Shot%202020-09-01%20at%203.26.37%20pm.png)

通过 Execution Plan，可以看到，对于整个 TiDB 集群，该 tpc-h 请求已经被合理地规划，即尽可能地减少数据返回。例如，内层查询的结果已经通过 Selection 和 Projection 并减少了返回的数据。在此基础上，需要查看源码，找到 Selection 和 Projection 的具体位置（是在 TiDB 还是 TiKV），以及能否利用查询的某些特征来优化类似查询。

## 04 | 其他

- 在某些时刻，AlertManager 无法找到其配置文件，以至于其无法启动集群。
