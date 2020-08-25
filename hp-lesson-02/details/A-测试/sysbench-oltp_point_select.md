# sysbench

## 数据

```shell
sysbench oltp_update_non_index --config-file=config --threads=32 --tables=32 --table_size=10000 prepare
```

## Point Select

### Threads = 1

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 1
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 1 tps: 1294.59 qps: 1294.59 (r/w/o: 1294.59/0.00/0.00) lat (ms,95%): 0.92 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 1 tps: 1295.35 qps: 1295.35 (r/w/o: 1295.35/0.00/0.00) lat (ms,95%): 0.94 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 1 tps: 1318.90 qps: 1318.90 (r/w/o: 1318.90/0.00/0.00) lat (ms,95%): 0.90 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 1 tps: 1284.41 qps: 1284.41 (r/w/o: 1284.41/0.00/0.00) lat (ms,95%): 0.94 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 1 tps: 1284.00 qps: 1284.00 (r/w/o: 1284.00/0.00/0.00) lat (ms,95%): 0.94 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 1 tps: 1303.20 qps: 1303.20 (r/w/o: 1303.20/0.00/0.00) lat (ms,95%): 0.92 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 1 tps: 1290.50 qps: 1290.50 (r/w/o: 1290.50/0.00/0.00) lat (ms,95%): 0.94 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 1 tps: 1249.50 qps: 1249.50 (r/w/o: 1249.50/0.00/0.00) lat (ms,95%): 0.97 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 1 tps: 1238.09 qps: 1238.09 (r/w/o: 1238.09/0.00/0.00) lat (ms,95%): 0.97 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            128210
        write:                           0
        other:                           0
        total:                           128210
    transactions:                        128210 (1282.05 per sec.)
    queries:                             128210 (1282.05 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0025s
    total number of events:              128210

Latency (ms):
         min:                                    0.52
         avg:                                    0.78
         max:                                   26.34
         95th percentile:                        0.94
         sum:                                99836.53

Threads fairness:
    events (avg/stddev):           128210.0000/0.00
    execution time (avg/stddev):   99.8365/0.00
```

### Threads = 8

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=8

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 8
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 8 tps: 10002.32 qps: 10002.32 (r/w/o: 10002.32/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 8 tps: 10073.62 qps: 10073.62 (r/w/o: 10073.62/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 8 tps: 9720.59 qps: 9720.59 (r/w/o: 9720.59/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 8 tps: 8534.74 qps: 8534.74 (r/w/o: 8534.74/0.00/0.00) lat (ms,95%): 1.47 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 8 tps: 9993.24 qps: 9993.24 (r/w/o: 9993.24/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 8 tps: 9884.82 qps: 9884.82 (r/w/o: 9884.82/0.00/0.00) lat (ms,95%): 1.25 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 8 tps: 9624.21 qps: 9624.21 (r/w/o: 9624.21/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 8 tps: 9995.54 qps: 9995.54 (r/w/o: 9995.54/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 8 tps: 9841.86 qps: 9841.86 (r/w/o: 9841.86/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 8 tps: 10075.46 qps: 10075.46 (r/w/o: 10075.46/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            977492
        write:                           0
        other:                           0
        total:                           977492
    transactions:                        977492 (9774.29 per sec.)
    queries:                             977492 (9774.29 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0048s
    total number of events:              977492

Latency (ms):
         min:                                    0.43
         avg:                                    0.82
         max:                                   11.53
         95th percentile:                        1.25
         sum:                               799147.23

Threads fairness:
    events (avg/stddev):           122186.5000/229.50
    execution time (avg/stddev):   99.8934/0.00
```

### Threads = 16

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=16

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 16
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 16 tps: 20734.94 qps: 20734.94 (r/w/o: 20734.94/0.00/0.00) lat (ms,95%): 1.01 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 16 tps: 17809.02 qps: 17809.02 (r/w/o: 17809.02/0.00/0.00) lat (ms,95%): 1.32 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 16 tps: 20405.71 qps: 20405.71 (r/w/o: 20405.71/0.00/0.00) lat (ms,95%): 1.04 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 16 tps: 20516.87 qps: 20516.87 (r/w/o: 20516.87/0.00/0.00) lat (ms,95%): 1.03 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 16 tps: 20695.30 qps: 20695.30 (r/w/o: 20695.30/0.00/0.00) lat (ms,95%): 1.04 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 16 tps: 20873.46 qps: 20873.56 (r/w/o: 20873.56/0.00/0.00) lat (ms,95%): 1.04 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 16 tps: 19942.26 qps: 19942.26 (r/w/o: 19942.26/0.00/0.00) lat (ms,95%): 1.12 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 16 tps: 20590.14 qps: 20590.04 (r/w/o: 20590.04/0.00/0.00) lat (ms,95%): 1.08 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 16 tps: 20685.46 qps: 20685.46 (r/w/o: 20685.46/0.00/0.00) lat (ms,95%): 1.06 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 16 tps: 20323.64 qps: 20323.64 (r/w/o: 20323.64/0.00/0.00) lat (ms,95%): 1.10 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            2025833
        write:                           0
        other:                           0
        total:                           2025833
    transactions:                        2025833 (20256.24 per sec.)
    queries:                             2025833 (20256.24 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0086s
    total number of events:              2025833

Latency (ms):
         min:                                    0.40
         avg:                                    0.79
         max:                                   25.14
         95th percentile:                        1.10
         sum:                              1598527.22

Threads fairness:
    events (avg/stddev):           126614.5625/222.15
    execution time (avg/stddev):   99.9080/0.00
```

### Threads = 24

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=24

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 24
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 24 tps: 28677.83 qps: 28677.83 (r/w/o: 28677.83/0.00/0.00) lat (ms,95%): 1.21 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 24 tps: 27613.83 qps: 27613.83 (r/w/o: 27613.83/0.00/0.00) lat (ms,95%): 1.30 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 24 tps: 29972.25 qps: 29972.25 (r/w/o: 29972.25/0.00/0.00) lat (ms,95%): 1.16 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 24 tps: 28478.83 qps: 28478.83 (r/w/o: 28478.83/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 24 tps: 28429.74 qps: 28429.74 (r/w/o: 28429.74/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 24 tps: 28071.90 qps: 28071.90 (r/w/o: 28071.90/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 24 tps: 29827.58 qps: 29827.58 (r/w/o: 29827.58/0.00/0.00) lat (ms,95%): 1.14 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 24 tps: 31311.77 qps: 31311.77 (r/w/o: 31311.77/0.00/0.00) lat (ms,95%): 1.06 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 24 tps: 31093.04 qps: 31093.04 (r/w/o: 31093.04/0.00/0.00) lat (ms,95%): 1.06 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 24 tps: 30924.12 qps: 30924.12 (r/w/o: 30924.12/0.00/0.00) lat (ms,95%): 1.08 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            2944098
        write:                           0
        other:                           0
        total:                           2944098
    transactions:                        2944098 (29434.97 per sec.)
    queries:                             2944098 (29434.97 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0187s
    total number of events:              2944098

Latency (ms):
         min:                                    0.39
         avg:                                    0.81
         max:                                   62.86
         95th percentile:                        1.18
         sum:                              2398156.83

Threads fairness:
    events (avg/stddev):           122670.7500/316.15
    execution time (avg/stddev):   99.9232/0.00
```

### Threads = 32

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=32

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 32
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 32 tps: 36809.67 qps: 36809.67 (r/w/o: 36809.67/0.00/0.00) lat (ms,95%): 1.25 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 32 tps: 36920.93 qps: 36920.93 (r/w/o: 36920.93/0.00/0.00) lat (ms,95%): 1.18 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 32 tps: 37183.90 qps: 37183.90 (r/w/o: 37183.90/0.00/0.00) lat (ms,95%): 1.16 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 32 tps: 34889.30 qps: 34889.30 (r/w/o: 34889.30/0.00/0.00) lat (ms,95%): 1.34 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 32 tps: 35599.64 qps: 35599.64 (r/w/o: 35599.64/0.00/0.00) lat (ms,95%): 1.34 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 32 tps: 37272.06 qps: 37272.06 (r/w/o: 37272.06/0.00/0.00) lat (ms,95%): 1.27 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 32 tps: 39282.74 qps: 39282.74 (r/w/o: 39282.74/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 32 tps: 39080.53 qps: 39080.53 (r/w/o: 39080.53/0.00/0.00) lat (ms,95%): 1.23 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 32 tps: 39071.61 qps: 39071.61 (r/w/o: 39071.61/0.00/0.00) lat (ms,95%): 1.25 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 32 tps: 37079.21 qps: 37079.21 (r/w/o: 37079.21/0.00/0.00) lat (ms,95%): 1.32 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            3732010
        write:                           0
        other:                           0
        total:                           3732010
    transactions:                        3732010 (37314.37 per sec.)
    queries:                             3732010 (37314.37 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0137s
    total number of events:              3732010

Latency (ms):
         min:                                    0.38
         avg:                                    0.86
         max:                                  102.41
         95th percentile:                        1.27
         sum:                              3197622.67

Threads fairness:
    events (avg/stddev):           116625.3125/249.33
    execution time (avg/stddev):   99.9257/0.00
```

### Threads = 40

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=40

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 40
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 40 tps: 43384.72 qps: 43384.72 (r/w/o: 43384.72/0.00/0.00) lat (ms,95%): 1.37 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 40 tps: 43669.96 qps: 43669.96 (r/w/o: 43669.96/0.00/0.00) lat (ms,95%): 1.34 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 40 tps: 43216.32 qps: 43216.32 (r/w/o: 43216.32/0.00/0.00) lat (ms,95%): 1.34 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 40 tps: 44399.64 qps: 44399.64 (r/w/o: 44399.64/0.00/0.00) lat (ms,95%): 1.32 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 40 tps: 44289.19 qps: 44289.19 (r/w/o: 44289.19/0.00/0.00) lat (ms,95%): 1.37 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 40 tps: 44067.83 qps: 44067.83 (r/w/o: 44067.83/0.00/0.00) lat (ms,95%): 1.42 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 40 tps: 42635.53 qps: 42635.53 (r/w/o: 42635.53/0.00/0.00) lat (ms,95%): 1.50 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 40 tps: 44743.94 qps: 44743.94 (r/w/o: 44743.94/0.00/0.00) lat (ms,95%): 1.39 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 40 tps: 43733.79 qps: 43733.79 (r/w/o: 43733.79/0.00/0.00) lat (ms,95%): 1.44 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 40 tps: 42283.15 qps: 42283.15 (r/w/o: 42283.15/0.00/0.00) lat (ms,95%): 1.42 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            4364381
        write:                           0
        other:                           0
        total:                           4364381
    transactions:                        4364381 (43635.75 per sec.)
    queries:                             4364381 (43635.75 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0168s
    total number of events:              4364381

Latency (ms):
         min:                                    0.38
         avg:                                    0.92
         max:                                   32.81
         95th percentile:                        1.39
         sum:                              3997510.59

Threads fairness:
    events (avg/stddev):           109109.5250/434.28
    execution time (avg/stddev):   99.9378/0.00
```

### Threads = 48

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=48

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 48
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 48 tps: 46783.45 qps: 46783.45 (r/w/o: 46783.45/0.00/0.00) lat (ms,95%): 1.61 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 48 tps: 48023.47 qps: 48023.47 (r/w/o: 48023.47/0.00/0.00) lat (ms,95%): 1.50 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 48 tps: 48144.91 qps: 48144.91 (r/w/o: 48144.91/0.00/0.00) lat (ms,95%): 1.47 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 48 tps: 47566.92 qps: 47566.92 (r/w/o: 47566.92/0.00/0.00) lat (ms,95%): 1.44 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 48 tps: 45157.26 qps: 45157.26 (r/w/o: 45157.26/0.00/0.00) lat (ms,95%): 1.70 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 48 tps: 46935.73 qps: 46935.73 (r/w/o: 46935.73/0.00/0.00) lat (ms,95%): 1.52 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 48 tps: 47093.27 qps: 47093.27 (r/w/o: 47093.27/0.00/0.00) lat (ms,95%): 1.58 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 48 tps: 50199.05 qps: 50199.05 (r/w/o: 50199.05/0.00/0.00) lat (ms,95%): 1.39 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 48 tps: 50692.99 qps: 50692.99 (r/w/o: 50692.99/0.00/0.00) lat (ms,95%): 1.37 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 48 tps: 49528.74 qps: 49528.74 (r/w/o: 49528.74/0.00/0.00) lat (ms,95%): 1.44 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            4801425
        write:                           0
        other:                           0
        total:                           4801425
    transactions:                        4801425 (48003.71 per sec.)
    queries:                             4801425 (48003.71 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0203s
    total number of events:              4801425

Latency (ms):
         min:                                    0.38
         avg:                                    1.00
         max:                                   38.13
         95th percentile:                        1.50
         sum:                              4797303.96

Threads fairness:
    events (avg/stddev):           100029.6875/244.67
    execution time (avg/stddev):   99.9438/0.00
```

### Threads = 56

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=56

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 56
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 56 tps: 47516.05 qps: 47516.05 (r/w/o: 47516.05/0.00/0.00) lat (ms,95%): 1.89 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 56 tps: 46881.86 qps: 46881.86 (r/w/o: 46881.86/0.00/0.00) lat (ms,95%): 1.93 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 56 tps: 45499.45 qps: 45499.45 (r/w/o: 45499.45/0.00/0.00) lat (ms,95%): 2.30 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 56 tps: 47287.87 qps: 47287.87 (r/w/o: 47287.87/0.00/0.00) lat (ms,95%): 1.96 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 56 tps: 47109.28 qps: 47109.28 (r/w/o: 47109.28/0.00/0.00) lat (ms,95%): 1.86 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 56 tps: 46066.63 qps: 46066.63 (r/w/o: 46066.63/0.00/0.00) lat (ms,95%): 2.07 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 56 tps: 47527.39 qps: 47527.39 (r/w/o: 47527.39/0.00/0.00) lat (ms,95%): 1.76 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 56 tps: 47114.39 qps: 47114.39 (r/w/o: 47114.39/0.00/0.00) lat (ms,95%): 1.82 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 56 tps: 47108.34 qps: 47108.34 (r/w/o: 47108.34/0.00/0.00) lat (ms,95%): 1.82 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 56 tps: 47298.75 qps: 47298.75 (r/w/o: 47298.75/0.00/0.00) lat (ms,95%): 1.79 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            4694272
        write:                           0
        other:                           0
        total:                           4694272
    transactions:                        4694272 (46931.03 per sec.)
    queries:                             4694272 (46931.03 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0233s
    total number of events:              4694272

Latency (ms):
         min:                                    0.40
         avg:                                    1.19
         max:                                   33.81
         95th percentile:                        1.93
         sum:                              5597290.66

Threads fairness:
    events (avg/stddev):           83826.2857/429.44
    execution time (avg/stddev):   99.9516/0.01
```

### Threads = 64

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=64

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 64
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 64 tps: 50300.94 qps: 50300.94 (r/w/o: 50300.94/0.00/0.00) lat (ms,95%): 1.96 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 64 tps: 50578.84 qps: 50578.84 (r/w/o: 50578.84/0.00/0.00) lat (ms,95%): 1.96 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 64 tps: 50648.49 qps: 50648.49 (r/w/o: 50648.49/0.00/0.00) lat (ms,95%): 1.89 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 64 tps: 51228.76 qps: 51228.76 (r/w/o: 51228.76/0.00/0.00) lat (ms,95%): 1.86 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 64 tps: 51546.08 qps: 51546.08 (r/w/o: 51546.08/0.00/0.00) lat (ms,95%): 1.79 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 64 tps: 51284.85 qps: 51284.85 (r/w/o: 51284.85/0.00/0.00) lat (ms,95%): 1.82 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 64 tps: 51282.19 qps: 51282.19 (r/w/o: 51282.19/0.00/0.00) lat (ms,95%): 1.86 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 64 tps: 51416.15 qps: 51416.15 (r/w/o: 51416.15/0.00/0.00) lat (ms,95%): 1.82 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 64 tps: 50996.12 qps: 50996.12 (r/w/o: 50996.12/0.00/0.00) lat (ms,95%): 1.89 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 64 tps: 51086.20 qps: 51086.20 (r/w/o: 51086.20/0.00/0.00) lat (ms,95%): 1.89 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            5103864
        write:                           0
        other:                           0
        total:                           5103864
    transactions:                        5103864 (51023.92 per sec.)
    queries:                             5103864 (51023.92 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0271s
    total number of events:              5103864

Latency (ms):
         min:                                    0.39
         avg:                                    1.25
         max:                                   71.32
         95th percentile:                        1.89
         sum:                              6397270.80

Threads fairness:
    events (avg/stddev):           79747.8750/375.13
    execution time (avg/stddev):   99.9574/0.01
```

### Threads = 72

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=72

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 72
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 72 tps: 51726.83 qps: 51726.83 (r/w/o: 51726.83/0.00/0.00) lat (ms,95%): 2.18 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 72 tps: 52030.76 qps: 52030.76 (r/w/o: 52030.76/0.00/0.00) lat (ms,95%): 2.07 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 72 tps: 52531.34 qps: 52531.34 (r/w/o: 52531.34/0.00/0.00) lat (ms,95%): 2.03 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 72 tps: 52817.20 qps: 52817.20 (r/w/o: 52817.20/0.00/0.00) lat (ms,95%): 2.00 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 72 tps: 52116.45 qps: 52116.45 (r/w/o: 52116.45/0.00/0.00) lat (ms,95%): 2.11 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 72 tps: 51889.88 qps: 51889.88 (r/w/o: 51889.88/0.00/0.00) lat (ms,95%): 2.11 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 72 tps: 52139.54 qps: 52139.54 (r/w/o: 52139.54/0.00/0.00) lat (ms,95%): 2.07 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 72 tps: 52281.68 qps: 52281.68 (r/w/o: 52281.68/0.00/0.00) lat (ms,95%): 2.07 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 72 tps: 52693.07 qps: 52693.07 (r/w/o: 52693.07/0.00/0.00) lat (ms,95%): 2.03 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 72 tps: 53540.93 qps: 53540.93 (r/w/o: 53540.93/0.00/0.00) lat (ms,95%): 2.03 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            5237868
        write:                           0
        other:                           0
        total:                           5237868
    transactions:                        5237868 (52362.15 per sec.)
    queries:                             5237868 (52362.15 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0299s
    total number of events:              5237868

Latency (ms):
         min:                                    0.42
         avg:                                    1.37
         max:                                   32.09
         95th percentile:                        2.07
         sum:                              7197337.41

Threads fairness:
    events (avg/stddev):           72748.1667/387.82
    execution time (avg/stddev):   99.9630/0.01
```

### Threads = 80

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=80

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 80
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 80 tps: 52672.71 qps: 52672.71 (r/w/o: 52672.71/0.00/0.00) lat (ms,95%): 2.43 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 80 tps: 53396.92 qps: 53396.92 (r/w/o: 53396.92/0.00/0.00) lat (ms,95%): 2.35 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 80 tps: 53521.94 qps: 53521.94 (r/w/o: 53521.94/0.00/0.00) lat (ms,95%): 2.26 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 80 tps: 52567.51 qps: 52567.51 (r/w/o: 52567.51/0.00/0.00) lat (ms,95%): 2.35 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 80 tps: 53859.25 qps: 53859.25 (r/w/o: 53859.25/0.00/0.00) lat (ms,95%): 2.22 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 80 tps: 53327.47 qps: 53327.47 (r/w/o: 53327.47/0.00/0.00) lat (ms,95%): 2.35 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 80 tps: 53358.54 qps: 53358.54 (r/w/o: 53358.54/0.00/0.00) lat (ms,95%): 2.30 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 80 tps: 53941.40 qps: 53941.40 (r/w/o: 53941.40/0.00/0.00) lat (ms,95%): 2.22 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 80 tps: 53453.47 qps: 53453.47 (r/w/o: 53453.47/0.00/0.00) lat (ms,95%): 2.30 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 80 tps: 52235.52 qps: 52235.52 (r/w/o: 52235.52/0.00/0.00) lat (ms,95%): 2.48 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            5323601
        write:                           0
        other:                           0
        total:                           5323601
    transactions:                        5323601 (53193.80 per sec.)
    queries:                             5323601 (53193.80 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0761s
    total number of events:              5323601

Latency (ms):
         min:                                    0.41
         avg:                                    1.50
         max:                                   43.69
         95th percentile:                        2.35
         sum:                              7997522.83

Threads fairness:
    events (avg/stddev):           66545.0125/461.05
    execution time (avg/stddev):   99.9690/0.01
```

### Threads = 512

```shell
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=512

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 512
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 512 tps: 49766.74 qps: 49766.84 (r/w/o: 49766.84/0.00/0.00) lat (ms,95%): 23.52 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 512 tps: 55124.74 qps: 55124.64 (r/w/o: 55124.64/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 512 tps: 55648.94 qps: 55648.94 (r/w/o: 55648.94/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 512 tps: 54433.03 qps: 54433.03 (r/w/o: 54433.03/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 512 tps: 54569.94 qps: 54569.94 (r/w/o: 54569.94/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 512 tps: 56230.54 qps: 56230.54 (r/w/o: 56230.54/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 512 tps: 55421.10 qps: 55421.10 (r/w/o: 55421.10/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 512 tps: 54963.72 qps: 54963.72 (r/w/o: 54963.72/0.00/0.00) lat (ms,95%): 20.74 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 512 tps: 56108.32 qps: 56108.32 (r/w/o: 56108.32/0.00/0.00) lat (ms,95%): 20.37 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 512 tps: 55047.11 qps: 55047.11 (r/w/o: 55047.11/0.00/0.00) lat (ms,95%): 20.74 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            5473794
        write:                           0
        other:                           0
        total:                           5473794
    transactions:                        5473794 (54614.46 per sec.)
    queries:                             5473794 (54614.46 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.2241s
    total number of events:              5473794

Latency (ms):
         min:                                    0.47
         avg:                                    9.35
         max:                                  654.78
         95th percentile:                       20.74
         sum:                             51198214.99

Threads fairness:
    events (avg/stddev):           10691.0039/226.03
    execution time (avg/stddev):   99.9965/0.05
```

```
sysbench oltp_point_select run --config-file=config --tables=32 --table-size=10000 --threads=640

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 640
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 640 tps: 49072.14 qps: 49072.04 (r/w/o: 49072.04/0.00/0.00) lat (ms,95%): 34.33 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 640 tps: 53113.87 qps: 53113.97 (r/w/o: 53113.97/0.00/0.00) lat (ms,95%): 27.17 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 640 tps: 53793.05 qps: 53793.15 (r/w/o: 53793.15/0.00/0.00) lat (ms,95%): 26.20 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 640 tps: 52764.47 qps: 52764.37 (r/w/o: 52764.37/0.00/0.00) lat (ms,95%): 27.17 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 640 tps: 54042.82 qps: 54042.82 (r/w/o: 54042.82/0.00/0.00) lat (ms,95%): 26.20 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 640 tps: 53781.68 qps: 53781.68 (r/w/o: 53781.68/0.00/0.00) lat (ms,95%): 25.74 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 640 tps: 54153.08 qps: 54153.08 (r/w/o: 54153.08/0.00/0.00) lat (ms,95%): 26.20 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 640 tps: 54770.92 qps: 54770.92 (r/w/o: 54770.92/0.00/0.00) lat (ms,95%): 26.20 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 640 tps: 54617.84 qps: 54617.74 (r/w/o: 54617.74/0.00/0.00) lat (ms,95%): 26.20 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 640 tps: 54912.74 qps: 54912.84 (r/w/o: 54912.84/0.00/0.00) lat (ms,95%): 25.74 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            5350977
        write:                           0
        other:                           0
        total:                           5350977
    transactions:                        5350977 (53371.84 per sec.)
    queries:                             5350977 (53371.84 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.2567s
    total number of events:              5350977

Latency (ms):
         min:                                    0.47
         avg:                                   11.96
         max:                                  728.89
         95th percentile:                       26.68
         sum:                             64011230.25

Threads fairness:
    events (avg/stddev):           8360.9016/136.16
    execution time (avg/stddev):   100.0175/0.07
```

## Update Index

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

```

Threads = 128

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=128

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 128
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 128 tps: 1362.78 qps: 1362.78 (r/w/o: 0.00/1362.78/0.00) lat (ms,95%): 121.08 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 128 tps: 1306.54 qps: 1306.54 (r/w/o: 0.00/1306.54/0.00) lat (ms,95%): 125.52 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 128 tps: 1360.11 qps: 1360.11 (r/w/o: 0.00/1360.11/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 128 tps: 1459.50 qps: 1459.50 (r/w/o: 0.00/1459.50/0.00) lat (ms,95%): 106.75 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 128 tps: 1453.90 qps: 1453.90 (r/w/o: 0.00/1453.90/0.00) lat (ms,95%): 108.68 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 128 tps: 1412.09 qps: 1412.09 (r/w/o: 0.00/1412.09/0.00) lat (ms,95%): 114.72 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 128 tps: 1439.21 qps: 1439.21 (r/w/o: 0.00/1439.21/0.00) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 128 tps: 1457.39 qps: 1457.39 (r/w/o: 0.00/1457.39/0.00) lat (ms,95%): 108.68 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 128 tps: 1396.60 qps: 1396.60 (r/w/o: 0.00/1396.60/0.00) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 128 tps: 1394.61 qps: 1394.61 (r/w/o: 0.00/1394.61/0.00) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           140558
        other:                           0
        total:                           140558
    transactions:                        140558 (1401.86 per sec.)
    queries:                             140558 (1401.86 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.2637s
    total number of events:              140558

Latency (ms):
         min:                                   47.72
         avg:                                   91.11
         max:                                 1218.70
         95th percentile:                      118.92
         sum:                             12806826.36

Threads fairness:
    events (avg/stddev):           1098.1094/12.92
    execution time (avg/stddev):   100.0533/0.04
```
