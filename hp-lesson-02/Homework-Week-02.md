# Homework | Week 02

## 00 | TLDR;

## 01 | 目的

- 分析 TiDB 的可能性能瓶颈
  - 部署 TiDB 集群
  - 使用 `sysbench`, `go-ycsb`, 和 `Go TPC` 对 TiDB 集群进行性能测试
  - 根据测试结果改变集群的配置参数

## 02 | 思路

本次作业需要分析 TiDB 的性能瓶颈。这主要是一个优化任务，需要对 TiDB 集群不断进行性能测试，并根据测试结果改变 TiDB 集群的配置，从而获得尽可能好的测试结果，进而分析集群的性能瓶颈。

可变量：

- TiDB 集群硬件架构及配置
  - 其中值得关注的是 CPU 数量 和 内存大小
- TiDB 集群配置
- 性能测试配置

由于时间有限，并且本次作业有过多 “隐藏任务”，以下操作固定 “TiDB 集群硬件架构及配置”，并在尽可能少地改变 “性能测试配置” 的情况下，更改 “TiDB 集群配置”。因此，本次作业的任务被重新定义为：_在特定的硬架构件下，通过性能测试优化 TiDB 集群配置，并分析性能瓶颈_。

### 操作步骤

1. 脚本化公有云硬件部署
2. 初始化公有云主机
3. 使用默认配置部署 TiDB 集群
4. 使用 [Lesson 02：对 TiDB 进行基准测试](https://www.bilibili.com/video/BV1TD4y1m7AF) 中的测试配置，进行测试，并获得 Baseline 测试结果
5. 根据需要更改测试配置，进行测试，并获得测试结果
6. 根据测试结果，更改 TiDB 集群配置
7. 使用更改后的配置，更新 TiDB 集群，并重复操作步骤 5-7
8. 分析 TiDB 集群可能的性能瓶颈所在

## 03 | 步骤

### 测试环境

- 云平台：Google Cloud
- 虚拟主机类型：`n1-standard-8`
  - vCPU 数：**8**
  - 内存：**30GB**
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

### Z | 测试

**_TiDB 集群默认配置_**

- [TiDB 集群默认配置](./details/Z-测试/topology.yaml)
  - 配置文件只定义集群拓扑结构，其他配置参数均使用默认值

**_Baseline 测试_**

- [sysbench 测试](./details/Z-测试/sysbench.md)
  - tps 在 1200 ~ 1300，可以尝试增加测试线程数以提高并发度，以达到 TiDB 集群的极限
- [go-ycsb 测试](./details/Z-测试/go-ycsb.md)
  - workload-a 在 recordcount 为 10000 时
- [go-tpc 测试](./details/Z-测试/go-tpc.md)
  - Warehouse 数量为 8 时，tpmC 为 479.7

### A | 测试

**_TiDB 集群默认配置_**

TiDB 集群依然使用默认配置。在 Z | 测试 的基础上，通过不断增加线程数，达到逐渐增加测试并发量的目的。

**_测试结果_**

每台虚拟机的 vCPU 数量为（8）限制了并发量，在以下测试中，当线程数量增加时，很快就会达到 tps 与 qps 的最高值并开始下降。

**sysbench**

Table Size: 10000

`oltp_point_select`

| #Thread | tps      | qps      | min latency | avg latency | 95th latency | max latency |
| ------- | -------- | -------- | ----------- | ----------- | ------------ | ----------- |
| 1       | 1282.05  | 1282.05  | 0.52        | 0.78        | 0.94         | 26.34       |
| 64      | 51023.92 | 51023.92 | 0.39        | 1.25        | 1.89         | 71.32       |
| 128     | 55566.28 | 55566.28 | 0.43        | 2.30        | 4.41         | 106.22      |
| 512     | 54614.46 | 54614.46 | 0.47        | 9.35        | 20.74        | 654.78      |
| 640     | 53371.84 | 53371.84 | 0.47        | 11.96       | 26.68        | 728.89      |

`oltp_update_index`

| #Thread | tps            | qps     | min latency | avg latency | 95th latency | max latency |
| ------- | -------------- | ------- | ----------- | ----------- | ------------ | ----------- |
| 1       | 34.02          | 34.02   | 23.07       | 29.39       | 38.25        | 59.08       |
| 64      | 767.74         | 767.74  | 48.70       | 83.27       | 101.13       | 676.55      |
| 128     | 1371.09        | 1371.09 | 49.00       | 93.12       | 121.08       | 881.66      |
| 256     | 2519.89        | 2519.89 | 47.20       | 101.30      | 144.97       | 1549.25     |
| 512     | 4318.67        | 4318.67 | 49.39       | 118.09      | 277.21       | 2939.08     |
| 600     | 4847.60        | 4847.60 | 50.20       | 122.51      | 369.77       | 4084.86     |
| 800     | Write Conflict |         |             |             |              |             |

`oltp_write_only`

| #Thread | tps    | qps     | min latency | avg latency | 95th latency | max latency |
| ------- | ------ | ------- | ----------- | ----------- | ------------ | ----------- |
| 1       | 9.67   | 58.01   | 79.65       | 103.43      | 121.08       | 156.38      |
| 64      | 288.73 | 1732.39 | 141.85      | 221.09      | 331.91       | 812.23      |
| 128     | 514.80 | 3088.79 | 151.54      | 248.02      | 411.96       | 1294.31     |
| 256     | 874.51 | 5247.30 | 142.48      | 291.63      | 569.67       | 2031.04     |
| 512     | 744.39 | 4466.87 | 138.86      | 665.56      | 2778.39      | 13551.06    |
| 600     | 556.07 | 3337.41 | 148.00      | 1053.72     | 4943.53      | 22525.45    |
| 800     | 275.94 | 1657.30 | 127.21      | 2767.52     | 13550.80     | 49213.67    |

`oltp_read_write`

| #Thread | tps    | qps      | min latency | avg latency | 95th latency | max latency |
| ------- | ------ | -------- | ----------- | ----------- | ------------ | ----------- |
| 1       | 10.10  | 201.93   | 80.13       | 99.03       | 116.80       | 150.25      |
| 64      | 192.11 | 3842.42  | 159.71      | 332.35      | 530.08       | 950.66      |
| 128     | 302.61 | 6052.30  | 168.35      | 421.58      | 682.06       | 1479.76     |
| 256     | 434.80 | 8696.05  | 172.05      | 585.76      | 909.80       | 1806.61     |
| 512     | 577.76 | 11555.78 | 193.94      | 878.73      | 1280.93      | 2797.73     |
| 600     | 596.18 | 11923.57 | 194.46      | 996.67      | 1453.01      | 2735.52     |
| 800     | 624.38 | 12488.79 | 237.31      | 1267.38     | 1869.60      | 3953.49     |

### B | 测试

**_测试配置_**

Table Size: 10000000

使用 32 个 线程 向 32 张表插入 10000000 条数据时，TiKV 处于如下状态

![TiKV 在插入数据时的状态](static/sql/Screen%20Shot%202020-08-24%20at%209.18.21%20pm.png)

- CPU 接近 100%
- 内存使用率缓慢上升，但始终低于 50%（15GB）
- 三个 TiKV 实例的 Region 数量同步增长

![gRPC 在插入数据时的状态](static/sql/Screen%20Shot%202020-08-24%20at%209.35.25%20pm.png)

- gRPC 的 message duration 相对较长，而这些 gRPC 大都是和分布式事务相关的通信

**_测试结果_**

数据插入耗时过长，无法进行测试

### 分析

**_可能瓶颈 1 - TiDB 对结果集的处理_**

对于一个 TiDB 集群，不同的输入对应着不同的压力，在本次作业中最直接的例子就是 tpc-h 测试。

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

**_可能瓶颈 2 - 分布式事务处理_**

在前文 “B | 测试” 中，当向 TiDB 集群插入大量数据（32 张表，每张表 10000000 条数据）时，耗时较长。其中，TiKV 集群中，CPU 利用率持续在 90% 左右，内存利用率缓慢升高，并持续低于 50%；但是 gRPC 的时长相对较长，可能是导致插入数据耗时长的主因。这里 Raft 共识算法基于 gRPC 实现，恰恰解释了 一些 gRPC 耗时长的原因，即分布式事务的特点。需要排除网络延迟等因素来确认 gRPC 的速度。此处瓶颈位于 TiKV 集群的分布式逻辑层，涉及 gRPC 及依赖于 gRPC 进行通信的模块。

## 04 | 其他

- 大量的时间和金钱花在了测试环境上
- 没有时间将测试结果对应到源码中
- 本次作业任务量更适合全职开发人员，而不适合笔者在业余时间对开源项目入门