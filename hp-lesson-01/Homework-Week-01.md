# Homework

## 00 | TLDR；

本次作业由以下步骤完成：

- 获取源码，并编译 PD，TiKV，TiDB 三个组件为二进制文件（分别为 pd-server，tikv-server，和 tidb-server）
- 运行三个组件 pd-server（\*1），tikv-server（\*3），和 tidb-server（\*1）
- 更改 TiDB 源码，使得 ”启动 TiDB 事务 时，打印日志 ’hello transaction‘“


## 01 | 目的

这次作业的根本目的是：更改 TiDB 源码，使得 ”启动 TiDB 事务 时，打印日志 ’hello transaction‘“

通过这个过程，可以：

- 初步了解 TiDB 集群的最基本组成，即 PD，TiKV，TiDB 三个组件，以及它们之间的关系；
- 理清 TiDB 的基本架构；
- 确定客户端 SQL 指令在 TiDB 中的大致执行流程

## 02 | 思路

由于是首次对 TiDB 源码进行改动，并且需要从头开始搭建本地运行环境，本次作业需要划分为一个个独立步骤完成。

一下为步骤划分：

1. 获取源码，并编译 PD，TiKV，TiDB 三个组件为二进制文件（分别为 pd-server，tikv-server，和 tidb-server）
2. 运行三个组件 pd-server（\*1），tikv-server（\*3），和 tidb-server（\*1）
3. 更改 TiDB 源码，使得 ”启动 TiDB 事务 时，打印日志 ’hello transaction‘“

其中 第 3 步 最为复杂，因为需要确定添加日志的位置。

TiDB 作为整个集群的入口组件，负责接收并响应来自客户端的指令，并且这些指令符合 MySQL 协议。作为一个”服务器“，TiDB 内部应该有一个 goroutine 负责分发来自客户端的指令，而得到这个任务（指令）的 goroutine 会根据 MySQL 协议 来解析这个任务，并且做出响应的操作。而 ”启动事务“ 就是其中一条指令。根据 [MySQL 的文档](https://dev.mysql.com/doc/refman/8.0/en/commit.html)），这条指令是 `START TRANSACTION` 或者 `BEGIN` 。所以，任务变为 ”在处理  `START TRANSACTION` 或者 `BEGIN` 指令的函数中插入日志“。

- [TiDB 源码阅读系列文章（三）SQL 的一生](https://pingcap.com/blog-cn/tidb-source-code-reading-3/) 证实了以上猜想
- [parser/parser.y](https://github.com/pingcap/parser/blob/a4bff035d3e2e980ebe8aa637bed9c03d9dac801/parser.y#L2430) 说明  `START TRANSACTION` 和 `BEGIN` 经过语法分析后被解析为同样的结构，即 `BeginStmt`
- [tidb/executor/simple.go](https://github.com/youwithouto/tidb/blob/baedc336afa26c85bbc9c865547789cce31597b0/executor/simple.go#L54) 定义了 `BeginStmt` 的语义

## 03 | 具体操作

### A | 获取源码 & 编译

以下步骤使用 `v4.0.4` 作为”稳定版本“

#### PD

- Fork 源码到私人的 GitHub 账户
    - [youwithouto/pd](https://github.com/youwithouto/pd)
- Clone 到本地并 Checkout 稳定版本 v4.0.4
    - `git clone [https://github.com/youwithouto/pd](https://github.com/youwithouto/pd)`
    - `git checkout -b release-v4.0.4 v4.0.4`
- 本地编译
    - `make build`
    - 二进制文件 `bin/pd-server`

#### TiKV

- Fork 源码到私人的 GitHub 账户
    - [youwithouto/tikv](https://github.com/youwithouto/tikv)
- Clone 到本地并 Checkout 稳定版本 v4.0.4
    - `git clone [https://github.com/youwithouto/tikv](https://github.com/youwithouto/tikv)`
    - `git checkout -b release-v4.0.4 v4.0.4`
- 本地编译
    - `make build`
    - 二进制文件 `target/debug/tikv-server`

#### TiDB

- Fork 源码到私人的 GitHub 账户
    - [youwithouto/tidb](https://github.com/youwithouto/tidb)
- Clone 到本地并 Checkout 稳定版本 v4.0.4
    - `git clone [https://github.com/youwithouto/tidb](https://github.com/youwithouto/tidb)`
    - `git checkout -b release-v4.0.4 v4.0.4`
- 本地编译
    - `make`
    - 二进制文件 `bin/tidb-server`

### B | 运行三个组件 pd-server，tikv-server，和 tidb-server

使用 `tiup` 运行集群

- [tiup/README.md](https://github.com/pingcap/tiup/blob/master/doc/user/README.md)

```bash
tiup playground --pd.binpath /xx/pd-server --kv.binpath /xx/tikv-server --kv 3 --db.binpath /xx/tidb-server
```

- [tiup/playground.md](https://github.com/pingcap/tiup/blob/master/doc/user/playground.md#replace-the-default-binary-file)
    - `--pd.binpath` 指定集群运行 pd-server 二进制文件位置
    - `--kv.binpath` 指定集群运行 tikv-server 二进制文件位置
    - `--kv 3` 指定集群运行 tikv-server 实例的数量为 3
    - `--db.binpath` 指定集群运行 tidb-server 二进制文件位置

### C | 更改 TiDB 源码，使得 ”启动 TiDB 事务 时，打印日志 ’hello transaction‘“

- 基于 TiDB 项目 `release-v4.0.4` 分支 创建 `homework-week-01` 分支
    - `git checkout -b homework-week-01 release-v4.0.4`
- 在 `executor/simple.go` 的 `executeBegin` 函数中添加日志
    - [tidb/executor/simple.go](https://github.com/youwithouto/tidb/blob/4bd361c5ab0976b68adab5656a95bacdecb03bed/executor/simple.go#L544)

## 04 | 其他

- 只有运行 PD 和 TiKV 的文档，没有找到手动运行 TiDB 的文档
    - [tikv/using-binary.md](https://github.com/tikv/tikv/blob/master/docs/how-to/deploy/using-binary.md)
    - 所以使用 `tiup` 运行集群
