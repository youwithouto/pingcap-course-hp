# sysbench

## 数据

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 1
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 1 tps: 9.70 qps: 58.28 (r/w/o: 0.00/38.79/19.49) lat (ms,95%): 118.92 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 1 tps: 9.50 qps: 57.10 (r/w/o: 0.00/38.10/19.00) lat (ms,95%): 125.52 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 1 tps: 9.70 qps: 58.50 (r/w/o: 0.00/39.10/19.40) lat (ms,95%): 121.08 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 1 tps: 9.70 qps: 58.00 (r/w/o: 0.00/38.60/19.40) lat (ms,95%): 121.08 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 1 tps: 9.70 qps: 58.40 (r/w/o: 0.00/39.00/19.40) lat (ms,95%): 114.72 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 1 tps: 9.80 qps: 58.40 (r/w/o: 0.00/38.80/19.60) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 1 tps: 9.50 qps: 57.40 (r/w/o: 0.00/38.40/19.00) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 1 tps: 9.60 qps: 57.20 (r/w/o: 0.00/38.00/19.20) lat (ms,95%): 125.52 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 1 tps: 9.60 qps: 58.00 (r/w/o: 0.00/38.80/19.20) lat (ms,95%): 121.08 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 1 tps: 9.80 qps: 58.80 (r/w/o: 0.00/39.20/19.60) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           3868
        other:                           1934
        total:                           5802
    transactions:                        967    (9.67 per sec.)
    queries:                             5802   (58.01 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0240s
    total number of events:              967

Latency (ms):
         min:                                   79.65
         avg:                                  103.43
         max:                                  156.38
         95th percentile:                      121.08
         sum:                               100016.25

Threads fairness:
    events (avg/stddev):           967.0000/0.00
    execution time (avg/stddev):   100.0163/0.00
```

## Update Index

### Threads = 1

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000


```

### Threads = 64

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=64
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 64
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 64 tps: 291.80 qps: 1771.62 (r/w/o: 0.00/1181.61/590.01) lat (ms,95%): 331.91 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 64 tps: 292.63 qps: 1752.57 (r/w/o: 0.00/1167.31/585.26) lat (ms,95%): 337.94 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 64 tps: 292.70 qps: 1760.50 (r/w/o: 0.00/1175.30/585.20) lat (ms,95%): 325.98 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 64 tps: 290.00 qps: 1737.92 (r/w/o: 0.00/1157.71/580.21) lat (ms,95%): 331.91 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 64 tps: 287.20 qps: 1725.30 (r/w/o: 0.00/1150.90/574.40) lat (ms,95%): 344.08 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 64 tps: 289.60 qps: 1736.00 (r/w/o: 0.00/1156.80/579.20) lat (ms,95%): 331.91 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 64 tps: 281.20 qps: 1687.79 (r/w/o: 0.00/1125.49/562.30) lat (ms,95%): 337.94 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 64 tps: 292.20 qps: 1754.20 (r/w/o: 0.00/1169.70/584.50) lat (ms,95%): 320.17 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 64 tps: 282.00 qps: 1692.00 (r/w/o: 0.00/1128.00/564.00) lat (ms,95%): 337.94 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 64 tps: 292.30 qps: 1752.71 (r/w/o: 0.00/1168.10/584.60) lat (ms,95%): 314.45 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           115924
        other:                           57962
        total:                           173886
    transactions:                        28981  (288.73 per sec.)
    queries:                             173886 (1732.39 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.3719s
    total number of events:              28981

Latency (ms):
         min:                                  141.85
         avg:                                  221.09
         max:                                  812.23
         95th percentile:                      331.91
         sum:                              6407448.15

Threads fairness:
    events (avg/stddev):           452.8281/4.44
    execution time (avg/stddev):   100.1164/0.08
```

### Threads = 128

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=128
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 128
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 128 tps: 505.03 qps: 3072.97 (r/w/o: 0.00/2050.21/1022.76) lat (ms,95%): 427.07 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 128 tps: 490.81 qps: 2944.89 (r/w/o: 0.00/1963.56/981.33) lat (ms,95%): 434.83 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 128 tps: 528.71 qps: 3170.04 (r/w/o: 0.00/2112.22/1057.81) lat (ms,95%): 419.45 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 128 tps: 510.39 qps: 3062.66 (r/w/o: 0.00/2041.87/1020.79) lat (ms,95%): 419.45 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 128 tps: 510.70 qps: 3060.91 (r/w/o: 0.00/2039.50/1021.40) lat (ms,95%): 419.45 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 128 tps: 549.60 qps: 3299.92 (r/w/o: 0.00/2200.71/1099.21) lat (ms,95%): 383.33 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 128 tps: 545.20 qps: 3273.59 (r/w/o: 0.00/2183.20/1090.40) lat (ms,95%): 383.33 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 128 tps: 524.00 qps: 3140.90 (r/w/o: 0.00/2092.90/1048.00) lat (ms,95%): 411.96 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 128 tps: 488.90 qps: 2933.22 (r/w/o: 0.00/1955.41/977.81) lat (ms,95%): 442.73 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 128 tps: 500.39 qps: 3006.46 (r/w/o: 0.00/2005.77/1000.69) lat (ms,95%): 427.07 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           206664
        other:                           103332
        total:                           309996
    transactions:                        51666  (514.80 per sec.)
    queries:                             309996 (3088.79 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.3599s
    total number of events:              51666

Latency (ms):
         min:                                  151.54
         avg:                                  248.02
         max:                                 1294.31
         95th percentile:                      411.96
         sum:                             12814414.50

Threads fairness:
    events (avg/stddev):           403.6406/5.34
    execution time (avg/stddev):   100.1126/0.07
```

### Threads = 256

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=256
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 256
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 256 tps: 883.99 qps: 5374.61 (r/w/o: 0.00/3580.94/1793.67) lat (ms,95%): 559.50 err/s: 0.10 reconn/s: 0.00
[ 20s ] thds: 256 tps: 892.13 qps: 5355.90 (r/w/o: 0.00/3571.53/1784.37) lat (ms,95%): 559.50 err/s: 0.10 reconn/s: 0.00
[ 30s ] thds: 256 tps: 884.61 qps: 5309.54 (r/w/o: 0.00/3540.13/1769.41) lat (ms,95%): 559.50 err/s: 0.20 reconn/s: 0.00
[ 40s ] thds: 256 tps: 905.88 qps: 5437.29 (r/w/o: 0.00/3625.63/1811.66) lat (ms,95%): 549.52 err/s: 0.20 reconn/s: 0.00
[ 50s ] thds: 256 tps: 895.82 qps: 5378.60 (r/w/o: 0.00/3586.67/1791.93) lat (ms,95%): 559.50 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 256 tps: 873.63 qps: 5239.07 (r/w/o: 0.00/3491.72/1747.36) lat (ms,95%): 569.67 err/s: 0.20 reconn/s: 0.00
[ 70s ] thds: 256 tps: 893.27 qps: 5357.70 (r/w/o: 0.00/3571.06/1786.63) lat (ms,95%): 549.52 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 256 tps: 868.00 qps: 5212.71 (r/w/o: 0.00/3476.71/1736.00) lat (ms,95%): 559.50 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 256 tps: 807.90 qps: 4846.50 (r/w/o: 0.00/3231.00/1615.50) lat (ms,95%): 623.33 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 256 tps: 860.19 qps: 5158.46 (r/w/o: 0.00/3437.77/1720.69) lat (ms,95%): 569.67 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           351662
        other:                           175832
        total:                           527494
    transactions:                        87912  (874.51 per sec.)
    queries:                             527494 (5247.30 per sec.)
    ignored errors:                      8      (0.08 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.5251s
    total number of events:              87912

Latency (ms):
         min:                                  142.48
         avg:                                  291.63
         max:                                 2031.04
         95th percentile:                      569.67
         sum:                             25638157.74

Threads fairness:
    events (avg/stddev):           343.4062/8.81
    execution time (avg/stddev):   100.1491/0.11
```

### Threads = 512

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=512
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 512
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 512 tps: 1153.89 qps: 7048.23 (r/w/o: 0.00/4689.75/2358.47) lat (ms,95%): 1089.30 err/s: 0.10 reconn/s: 0.00
[ 20s ] thds: 512 tps: 587.04 qps: 3511.76 (r/w/o: 0.00/2336.67/1175.09) lat (ms,95%): 3982.86 err/s: 0.40 reconn/s: 0.00
[ 30s ] thds: 512 tps: 476.18 qps: 2868.79 (r/w/o: 0.00/1916.13/952.66) lat (ms,95%): 5813.24 err/s: 0.30 reconn/s: 0.00
[ 40s ] thds: 512 tps: 922.43 qps: 5541.88 (r/w/o: 0.00/3697.32/1844.56) lat (ms,95%): 2279.14 err/s: 0.10 reconn/s: 0.00
[ 50s ] thds: 512 tps: 738.50 qps: 4418.12 (r/w/o: 0.00/2940.62/1477.51) lat (ms,95%): 2493.86 err/s: 0.10 reconn/s: 0.00
[ 60s ] thds: 512 tps: 706.60 qps: 4253.01 (r/w/o: 0.00/2839.40/1413.60) lat (ms,95%): 3841.98 err/s: 0.40 reconn/s: 0.00
[ 70s ] thds: 512 tps: 1146.97 qps: 6886.81 (r/w/o: 0.00/4593.27/2293.54) lat (ms,95%): 1280.93 err/s: 0.20 reconn/s: 0.00
[ 80s ] thds: 512 tps: 974.82 qps: 5835.03 (r/w/o: 0.00/3884.69/1950.34) lat (ms,95%): 1561.52 err/s: 0.20 reconn/s: 0.00
[ 90s ] thds: 512 tps: 485.50 qps: 2910.89 (r/w/o: 0.00/1939.99/970.90) lat (ms,95%): 4943.53 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 512 tps: 536.35 qps: 3222.00 (r/w/o: 0.00/2149.00/1073.00) lat (ms,95%): 4855.31 err/s: 0.20 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           311233
        other:                           155619
        total:                           466852
    transactions:                        77799  (744.39 per sec.)
    queries:                             466852 (4466.87 per sec.)
    ignored errors:                      21     (0.20 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          104.5127s
    total number of events:              77799

Latency (ms):
         min:                                  138.86
         avg:                                  665.56
         max:                                13551.06
         95th percentile:                     2778.39
         sum:                             51780007.06

Threads fairness:
    events (avg/stddev):           151.9512/15.30
    execution time (avg/stddev):   101.1328/1.12
```

### Threads = 600

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=600
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 600
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 600 tps: 1104.42 qps: 6769.49 (r/w/o: 0.00/4500.47/2269.03) lat (ms,95%): 1589.90 err/s: 0.20 reconn/s: 0.00
[ 20s ] thds: 600 tps: 577.13 qps: 3461.78 (r/w/o: 0.00/2307.42/1154.36) lat (ms,95%): 4437.27 err/s: 0.40 reconn/s: 0.00
[ 30s ] thds: 600 tps: 645.01 qps: 3862.86 (r/w/o: 0.00/2572.34/1290.52) lat (ms,95%): 3773.42 err/s: 0.20 reconn/s: 0.00
[ 40s ] thds: 600 tps: 530.60 qps: 3191.89 (r/w/o: 0.00/2130.40/1061.50) lat (ms,95%): 5409.26 err/s: 0.30 reconn/s: 0.00
[ 50s ] thds: 600 tps: 814.49 qps: 4881.77 (r/w/o: 0.00/3252.18/1629.59) lat (ms,95%): 2728.81 err/s: 0.60 reconn/s: 0.00
[ 60s ] thds: 600 tps: 462.50 qps: 2771.79 (r/w/o: 0.00/1846.40/925.40) lat (ms,95%): 4768.67 err/s: 0.40 reconn/s: 0.00
[ 70s ] thds: 600 tps: 234.20 qps: 1406.31 (r/w/o: 0.00/937.41/468.90) lat (ms,95%): 10158.80 err/s: 0.50 reconn/s: 0.00
[ 80s ] thds: 600 tps: 508.89 qps: 3062.05 (r/w/o: 0.00/2044.27/1017.78) lat (ms,95%): 7754.26 err/s: 0.20 reconn/s: 0.00
[ 90s ] thds: 600 tps: 435.81 qps: 2605.03 (r/w/o: 0.00/1732.72/872.31) lat (ms,95%): 6135.91 err/s: 0.50 reconn/s: 0.00
[ 100s ] thds: 600 tps: 427.79 qps: 2569.02 (r/w/o: 0.00/1713.14/855.87) lat (ms,95%): 6476.48 err/s: 0.40 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           232111
        other:                           116059
        total:                           348170
    transactions:                        58011  (556.07 per sec.)
    queries:                             348170 (3337.41 per sec.)
    ignored errors:                      37     (0.35 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          104.3216s
    total number of events:              58011

Latency (ms):
         min:                                  148.00
         avg:                                 1053.72
         max:                                22525.45
         95th percentile:                     4943.53
         sum:                             61127368.47

Threads fairness:
    events (avg/stddev):           96.6850/13.32
    execution time (avg/stddev):   101.8789/1.21

```

Threads = 800

```shell
sysbench oltp_write_only run --config-file=config --tables=32 --table-size=10000 --threads=800
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 800
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 800 tps: 816.61 qps: 5067.02 (r/w/o: 0.00/3353.82/1713.20) lat (ms,95%): 2632.28 err/s: 0.10 reconn/s: 0.00
[ 20s ] thds: 800 tps: 297.40 qps: 1787.43 (r/w/o: 0.00/1192.12/595.31) lat (ms,95%): 8795.93 err/s: 0.40 reconn/s: 0.00
[ 30s ] thds: 800 tps: 313.50 qps: 1877.17 (r/w/o: 0.00/1249.38/627.79) lat (ms,95%): 11732.86 err/s: 0.80 reconn/s: 0.00
[ 40s ] thds: 800 tps: 351.41 qps: 2107.86 (r/w/o: 0.00/1404.04/703.82) lat (ms,95%): 9799.46 err/s: 1.00 reconn/s: 0.00
[ 50s ] thds: 800 tps: 209.70 qps: 1263.02 (r/w/o: 0.00/843.01/420.01) lat (ms,95%): 13308.98 err/s: 0.60 reconn/s: 0.00
[ 60s ] thds: 800 tps: 161.50 qps: 971.00 (r/w/o: 0.00/647.20/323.80) lat (ms,95%): 16224.31 err/s: 0.80 reconn/s: 0.00
[ 70s ] thds: 800 tps: 179.60 qps: 1083.08 (r/w/o: 0.00/723.59/359.49) lat (ms,95%): 20503.50 err/s: 0.30 reconn/s: 0.00
[ 80s ] thds: 800 tps: 250.20 qps: 1502.62 (r/w/o: 0.00/1001.22/501.41) lat (ms,95%): 17435.99 err/s: 1.00 reconn/s: 0.00
[ 90s ] thds: 800 tps: 174.60 qps: 1044.29 (r/w/o: 0.00/694.50/349.80) lat (ms,95%): 16224.31 err/s: 0.70 reconn/s: 0.00
[ 100s ] thds: 800 tps: 155.70 qps: 935.21 (r/w/o: 0.00/623.11/312.10) lat (ms,95%): 18403.78 err/s: 0.60 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           119729
        other:                           59873
        total:                           179602
    transactions:                        29904  (275.94 per sec.)
    queries:                             179602 (1657.30 per sec.)
    ignored errors:                      65     (0.60 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          108.3682s
    total number of events:              29904

Latency (ms):
         min:                                  127.21
         avg:                                 2767.52
         max:                                49213.67
         95th percentile:                    13550.80
         sum:                             82759768.76

Threads fairness:
    events (avg/stddev):           37.3800/8.67
    execution time (avg/stddev):   103.4497/2.07

```

Threads = 1

```shell


```

Threads = 1

```shell


```

Threads = 1

```shell


```

Threads = 128

```shell

```
