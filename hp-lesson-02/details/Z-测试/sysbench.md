# sysbench

## 数据

```shell
sysbench oltp_update_non_index --config-file=config --threads=32 --tables=32 --table_size=10000 prepare
```

## Point Select

```shell
sysbench --config-file=config oltp_point_select --tables=32 --table-size=10000 run

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

## Update Index

```shell
sysbench --config-file=config oltp_update_index --threads=128 --tables=32 --table-size=10000 run

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