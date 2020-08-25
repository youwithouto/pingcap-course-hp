# sysbench

## 数据

```shell

```

## Update Index

### Threads = 1

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 1
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 1 tps: 9.40 qps: 188.65 (r/w/o: 132.17/37.59/18.90) lat (ms,95%): 127.81 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 1 tps: 9.90 qps: 197.41 (r/w/o: 138.01/39.60/19.80) lat (ms,95%): 118.92 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 1 tps: 10.10 qps: 203.80 (r/w/o: 142.80/40.80/20.20) lat (ms,95%): 110.66 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 1 tps: 10.50 qps: 209.70 (r/w/o: 147.00/41.70/21.00) lat (ms,95%): 106.75 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 1 tps: 10.20 qps: 204.30 (r/w/o: 142.80/41.10/20.40) lat (ms,95%): 110.66 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 1 tps: 9.80 qps: 195.80 (r/w/o: 137.20/39.00/19.60) lat (ms,95%): 125.52 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 1 tps: 10.20 qps: 203.70 (r/w/o: 142.70/40.60/20.40) lat (ms,95%): 114.72 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 1 tps: 10.30 qps: 206.00 (r/w/o: 144.20/41.20/20.60) lat (ms,95%): 108.68 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 1 tps: 10.30 qps: 205.70 (r/w/o: 143.90/41.20/20.60) lat (ms,95%): 110.66 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 1 tps: 10.20 qps: 204.80 (r/w/o: 143.20/41.20/20.40) lat (ms,95%): 112.67 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            14140
        write:                           4040
        other:                           2020
        total:                           20200
    transactions:                        1010   (10.10 per sec.)
    queries:                             20200  (201.93 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0326s
    total number of events:              1010

Latency (ms):
         min:                                   80.13
         avg:                                   99.03
         max:                                  150.25
         95th percentile:                      116.80
         sum:                               100021.35

Threads fairness:
    events (avg/stddev):           1010.0000/0.00
    execution time (avg/stddev):   100.0214/0.00


```

### Threads = 64

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=64
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 64
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 64 tps: 197.44 qps: 4045.58 (r/w/o: 2846.74/797.56/401.28) lat (ms,95%): 502.20 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 64 tps: 200.22 qps: 4005.10 (r/w/o: 2802.08/802.58/400.44) lat (ms,95%): 502.20 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 64 tps: 184.60 qps: 3685.49 (r/w/o: 2582.19/734.10/369.20) lat (ms,95%): 549.52 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 64 tps: 195.30 qps: 3923.63 (r/w/o: 2742.82/790.11/390.70) lat (ms,95%): 520.62 err/s: 0.10 reconn/s: 0.00
[ 50s ] thds: 64 tps: 199.40 qps: 3986.62 (r/w/o: 2790.35/797.48/398.79) lat (ms,95%): 502.20 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 64 tps: 198.90 qps: 3971.15 (r/w/o: 2782.23/791.11/397.80) lat (ms,95%): 511.33 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 64 tps: 197.90 qps: 3964.01 (r/w/o: 2775.41/792.80/395.80) lat (ms,95%): 511.33 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 64 tps: 182.90 qps: 3649.91 (r/w/o: 2553.41/730.70/365.80) lat (ms,95%): 559.50 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 64 tps: 184.20 qps: 3689.22 (r/w/o: 2580.31/740.50/368.40) lat (ms,95%): 559.50 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 64 tps: 182.10 qps: 3636.10 (r/w/o: 2549.30/722.60/364.20) lat (ms,95%): 580.02 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            270130
        write:                           77178
        other:                           38589
        total:                           385897
    transactions:                        19294  (192.11 per sec.)
    queries:                             385897 (3842.42 per sec.)
    ignored errors:                      1      (0.01 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.4291s
    total number of events:              19294

Latency (ms):
         min:                                  159.71
         avg:                                  332.35
         max:                                  950.66
         95th percentile:                      530.08
         sum:                              6412304.76

Threads fairness:
    events (avg/stddev):           301.4688/5.16
    execution time (avg/stddev):   100.1923/0.11
```

### Threads = 128

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=128
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 128
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 128 tps: 304.81 qps: 6294.69 (r/w/o: 4434.65/1237.62/622.41) lat (ms,95%): 669.89 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 128 tps: 303.93 qps: 6073.50 (r/w/o: 4248.22/1217.52/607.76) lat (ms,95%): 669.89 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 128 tps: 299.80 qps: 5998.45 (r/w/o: 4200.53/1198.21/599.70) lat (ms,95%): 682.06 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 128 tps: 304.50 qps: 6084.41 (r/w/o: 4260.90/1214.50/609.00) lat (ms,95%): 669.89 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 128 tps: 302.80 qps: 6051.32 (r/w/o: 4234.45/1211.28/605.59) lat (ms,95%): 694.45 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 128 tps: 300.00 qps: 5997.85 (r/w/o: 4202.36/1195.49/599.99) lat (ms,95%): 694.45 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 128 tps: 302.80 qps: 6054.74 (r/w/o: 4236.03/1213.11/605.60) lat (ms,95%): 682.06 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 128 tps: 308.71 qps: 6188.44 (r/w/o: 4330.50/1240.53/617.41) lat (ms,95%): 669.89 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 128 tps: 296.49 qps: 5933.88 (r/w/o: 4154.02/1186.88/592.99) lat (ms,95%): 682.06 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 128 tps: 306.20 qps: 6111.40 (r/w/o: 4278.73/1220.48/612.19) lat (ms,95%): 669.89 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            425992
        write:                           121712
        other:                           60856
        total:                           608560
    transactions:                        30428  (302.61 per sec.)
    queries:                             608560 (6052.30 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.5486s
    total number of events:              30428

Latency (ms):
         min:                                  168.35
         avg:                                  421.58
         max:                                 1479.76
         95th percentile:                      682.06
         sum:                             12827872.49

Threads fairness:
    events (avg/stddev):           237.7188/5.21
    execution time (avg/stddev):   100.2178/0.15
```

### Threads = 256

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=256
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 256
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 256 tps: 440.14 qps: 9137.34 (r/w/o: 6452.03/1779.65/905.67) lat (ms,95%): 861.95 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 256 tps: 439.37 qps: 8814.92 (r/w/o: 6171.12/1764.86/878.93) lat (ms,95%): 909.80 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 256 tps: 439.70 qps: 8792.28 (r/w/o: 6158.85/1754.02/879.41) lat (ms,95%): 893.56 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 256 tps: 428.09 qps: 8552.15 (r/w/o: 5987.69/1708.27/856.18) lat (ms,95%): 909.80 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 256 tps: 430.29 qps: 8603.04 (r/w/o: 6010.82/1731.65/860.57) lat (ms,95%): 926.33 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 256 tps: 440.02 qps: 8832.59 (r/w/o: 6188.85/1763.70/880.05) lat (ms,95%): 893.56 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 256 tps: 433.00 qps: 8624.04 (r/w/o: 6041.76/1716.29/865.99) lat (ms,95%): 909.80 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 256 tps: 433.29 qps: 8679.49 (r/w/o: 6076.95/1735.96/866.58) lat (ms,95%): 909.80 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 256 tps: 428.71 qps: 8613.05 (r/w/o: 6018.18/1737.45/857.43) lat (ms,95%): 909.80 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 256 tps: 447.70 qps: 8906.65 (r/w/o: 6245.77/1765.49/895.40) lat (ms,95%): 877.61 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            614040
        write:                           175440
        other:                           87720
        total:                           877200
    transactions:                        43860  (434.80 per sec.)
    queries:                             877200 (8696.05 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.8716s
    total number of events:              43860

Latency (ms):
         min:                                  172.05
         avg:                                  585.76
         max:                                 1806.61
         95th percentile:                      909.80
         sum:                             25691328.19

Threads fairness:
    events (avg/stddev):           171.3281/4.03
    execution time (avg/stddev):   100.3568/0.20
```

### Threads = 512

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=512
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 512
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 512 tps: 563.13 qps: 11932.89 (r/w/o: 8468.71/2286.93/1177.25) lat (ms,95%): 1258.08 err/s: 0.10 reconn/s: 0.00
[ 20s ] thds: 512 tps: 590.44 qps: 11786.78 (r/w/o: 8241.95/2363.96/1180.88) lat (ms,95%): 1258.08 err/s: 0.10 reconn/s: 0.00
[ 30s ] thds: 512 tps: 583.11 qps: 11657.91 (r/w/o: 8158.18/2334.32/1165.41) lat (ms,95%): 1280.93 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 512 tps: 580.40 qps: 11676.32 (r/w/o: 8182.22/2332.60/1161.50) lat (ms,95%): 1280.93 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 512 tps: 587.41 qps: 11723.93 (r/w/o: 8191.19/2358.33/1174.41) lat (ms,95%): 1304.21 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 512 tps: 578.88 qps: 11546.86 (r/w/o: 8090.99/2297.21/1158.66) lat (ms,95%): 1280.93 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 512 tps: 566.12 qps: 11367.81 (r/w/o: 7971.19/2264.28/1132.34) lat (ms,95%): 1327.91 err/s: 0.10 reconn/s: 0.00
[ 80s ] thds: 512 tps: 582.70 qps: 11672.32 (r/w/o: 8157.82/2349.10/1165.40) lat (ms,95%): 1280.93 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 512 tps: 588.39 qps: 11729.68 (r/w/o: 8207.22/2346.08/1176.39) lat (ms,95%): 1280.93 err/s: 0.10 reconn/s: 0.00
[ 100s ] thds: 512 tps: 579.40 qps: 11601.81 (r/w/o: 8128.53/2314.38/1158.89) lat (ms,95%): 1280.93 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            819238
        write:                           234058
        other:                           117030
        total:                           1170326
    transactions:                        58513  (577.76 per sec.)
    queries:                             1170326 (11555.78 per sec.)
    ignored errors:                      4      (0.04 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          101.2745s
    total number of events:              58513

Latency (ms):
         min:                                  193.94
         avg:                                  878.73
         max:                                 2797.73
         95th percentile:                     1280.93
         sum:                             51416847.83

Threads fairness:
    events (avg/stddev):           114.2832/3.15
    execution time (avg/stddev):   100.4235/0.29
```

### Threads = 600

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=600
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 600
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 600 tps: 577.21 qps: 12307.62 (r/w/o: 8726.98/2367.53/1213.11) lat (ms,95%): 1427.08 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 600 tps: 597.87 qps: 11961.26 (r/w/o: 8377.35/2387.57/1196.34) lat (ms,95%): 1453.01 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 600 tps: 607.89 qps: 12162.42 (r/w/o: 8515.17/2431.76/1215.48) lat (ms,95%): 1427.08 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 600 tps: 600.11 qps: 11984.70 (r/w/o: 8379.17/2406.12/1199.41) lat (ms,95%): 1427.08 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 600 tps: 590.69 qps: 11816.39 (r/w/o: 8279.72/2354.88/1181.79) lat (ms,95%): 1479.41 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 600 tps: 605.70 qps: 12133.45 (r/w/o: 8512.13/2410.91/1210.40) lat (ms,95%): 1453.01 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 600 tps: 614.30 qps: 12341.91 (r/w/o: 8643.81/2467.60/1230.50) lat (ms,95%): 1427.08 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 600 tps: 597.29 qps: 11888.90 (r/w/o: 8322.66/2371.76/1194.48) lat (ms,95%): 1453.01 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 600 tps: 599.69 qps: 12005.22 (r/w/o: 8402.57/2403.26/1199.38) lat (ms,95%): 1427.08 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 600 tps: 600.92 qps: 12003.36 (r/w/o: 8393.65/2408.57/1201.14) lat (ms,95%): 1453.01 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            847252
        write:                           242072
        other:                           121036
        total:                           1210360
    transactions:                        60518  (596.18 per sec.)
    queries:                             1210360 (11923.57 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          101.5082s
    total number of events:              60518

Latency (ms):
         min:                                  194.46
         avg:                                  996.67
         max:                                 2735.52
         95th percentile:                     1453.01
         sum:                             60316462.58

Threads fairness:
    events (avg/stddev):           100.8633/2.59
    execution time (avg/stddev):   100.5274/0.33

```

Threads = 800

```shell
sysbench oltp_read_write run --config-file=config --tables=32 --table-size=10000 --threads=800
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 800
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 800 tps: 586.53 qps: 12818.07 (r/w/o: 9144.34/2420.60/1253.14) lat (ms,95%): 1903.57 err/s: 0.10 reconn/s: 0.00
[ 20s ] thds: 800 tps: 641.29 qps: 12796.48 (r/w/o: 8956.21/2558.68/1281.59) lat (ms,95%): 1836.24 err/s: 0.10 reconn/s: 0.00
[ 30s ] thds: 800 tps: 636.24 qps: 12699.63 (r/w/o: 8896.11/2530.14/1273.37) lat (ms,95%): 1836.24 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 800 tps: 622.78 qps: 12448.76 (r/w/o: 8718.46/2484.63/1245.67) lat (ms,95%): 1869.60 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 800 tps: 620.02 qps: 12456.61 (r/w/o: 8709.79/2506.78/1240.04) lat (ms,95%): 1869.60 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 800 tps: 623.09 qps: 12370.74 (r/w/o: 8634.89/2491.37/1244.48) lat (ms,95%): 1869.60 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 800 tps: 643.21 qps: 12796.83 (r/w/o: 8964.09/2545.93/1286.81) lat (ms,95%): 1903.57 err/s: 0.10 reconn/s: 0.00
[ 80s ] thds: 800 tps: 635.02 qps: 12738.95 (r/w/o: 8922.54/2545.77/1270.63) lat (ms,95%): 1836.24 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 800 tps: 638.28 qps: 12872.22 (r/w/o: 9031.33/2563.32/1277.56) lat (ms,95%): 1869.60 err/s: 0.10 reconn/s: 0.00
[ 100s ] thds: 800 tps: 626.67 qps: 12520.43 (r/w/o: 8756.43/2510.57/1253.43) lat (ms,95%): 1869.60 err/s: 0.20 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            889560
        write:                           254143
        other:                           127073
        total:                           1270776
    transactions:                        63533  (624.38 per sec.)
    queries:                             1270776 (12488.79 per sec.)
    ignored errors:                      7      (0.07 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          101.7516s
    total number of events:              63533

Latency (ms):
         min:                                  237.31
         avg:                                 1267.38
         max:                                 3953.49
         95th percentile:                     1869.60
         sum:                             80520192.68

Threads fairness:
    events (avg/stddev):           79.4163/2.30
    execution time (avg/stddev):   100.6502/0.44
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
