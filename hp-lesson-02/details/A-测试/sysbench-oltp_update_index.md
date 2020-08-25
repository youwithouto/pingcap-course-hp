# sysbench

## 数据

```shell
sysbench oltp_update_non_index --config-file=config --threads=32 --tables=32 --table_size=10000 prepare
```

## Update Index

### Threads = 1

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000

sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 1
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 1 tps: 34.59 qps: 34.59 (r/w/o: 0.00/34.59/0.00) lat (ms,95%): 36.24 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 1 tps: 34.60 qps: 34.60 (r/w/o: 0.00/34.60/0.00) lat (ms,95%): 37.56 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 1 tps: 34.20 qps: 34.20 (r/w/o: 0.00/34.20/0.00) lat (ms,95%): 38.25 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 1 tps: 32.80 qps: 32.80 (r/w/o: 0.00/32.80/0.00) lat (ms,95%): 42.61 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 1 tps: 33.80 qps: 33.80 (r/w/o: 0.00/33.80/0.00) lat (ms,95%): 37.56 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 1 tps: 34.20 qps: 34.20 (r/w/o: 0.00/34.20/0.00) lat (ms,95%): 36.89 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 1 tps: 34.20 qps: 34.20 (r/w/o: 0.00/34.20/0.00) lat (ms,95%): 37.56 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 1 tps: 35.00 qps: 35.00 (r/w/o: 0.00/35.00/0.00) lat (ms,95%): 34.95 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 1 tps: 34.40 qps: 34.40 (r/w/o: 0.00/34.40/0.00) lat (ms,95%): 36.24 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 1 tps: 32.40 qps: 32.40 (r/w/o: 0.00/32.40/0.00) lat (ms,95%): 41.10 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           3403
        other:                           0
        total:                           3403
    transactions:                        3403   (34.02 per sec.)
    queries:                             3403   (34.02 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0273s
    total number of events:              3403

Latency (ms):
         min:                                   23.07
         avg:                                   29.39
         max:                                   59.08
         95th percentile:                       38.25
         sum:                               100008.07

Threads fairness:
    events (avg/stddev):           3403.0000/0.00
    execution time (avg/stddev):   100.0081/0.00
```

### Threads = 8

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=8
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 8
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 8 tps: 128.16 qps: 128.16 (r/w/o: 0.00/128.16/0.00) lat (ms,95%): 81.48 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 8 tps: 133.31 qps: 133.31 (r/w/o: 0.00/133.31/0.00) lat (ms,95%): 75.82 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 8 tps: 135.90 qps: 135.90 (r/w/o: 0.00/135.90/0.00) lat (ms,95%): 73.13 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 8 tps: 134.30 qps: 134.30 (r/w/o: 0.00/134.30/0.00) lat (ms,95%): 75.82 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 8 tps: 131.90 qps: 131.90 (r/w/o: 0.00/131.90/0.00) lat (ms,95%): 77.19 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 8 tps: 129.60 qps: 129.60 (r/w/o: 0.00/129.60/0.00) lat (ms,95%): 78.60 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 8 tps: 130.00 qps: 130.00 (r/w/o: 0.00/130.00/0.00) lat (ms,95%): 77.19 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 8 tps: 129.80 qps: 129.80 (r/w/o: 0.00/129.80/0.00) lat (ms,95%): 77.19 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 8 tps: 127.79 qps: 127.79 (r/w/o: 0.00/127.79/0.00) lat (ms,95%): 78.60 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 8 tps: 129.51 qps: 129.51 (r/w/o: 0.00/129.51/0.00) lat (ms,95%): 77.19 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           13111
        other:                           0
        total:                           13111
    transactions:                        13111  (131.03 per sec.)
    queries:                             13111  (131.03 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.0574s
    total number of events:              13111

Latency (ms):
         min:                                   35.81
         avg:                                   61.04
         max:                                  355.52
         95th percentile:                       77.19
         sum:                               800253.88

Threads fairness:
    events (avg/stddev):           1638.8750/6.11
    execution time (avg/stddev):   100.0317/0.01
```

### Threads = 16

```shell

```

### Threads = 24

```shell

```

### Threads = 32

```shell

```

### Threads = 40

```shell

```

### Threads = 48

```shell

```

### Threads = 56

```shell

```

### Threads = 64

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=64
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 64
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 64 tps: 772.04 qps: 772.04 (r/w/o: 0.00/772.04/0.00) lat (ms,95%): 101.13 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 64 tps: 778.21 qps: 778.21 (r/w/o: 0.00/778.21/0.00) lat (ms,95%): 102.97 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 64 tps: 758.70 qps: 758.70 (r/w/o: 0.00/758.70/0.00) lat (ms,95%): 101.13 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 64 tps: 769.49 qps: 769.49 (r/w/o: 0.00/769.49/0.00) lat (ms,95%): 99.33 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 64 tps: 761.99 qps: 761.99 (r/w/o: 0.00/761.99/0.00) lat (ms,95%): 102.97 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 64 tps: 762.22 qps: 762.22 (r/w/o: 0.00/762.22/0.00) lat (ms,95%): 102.97 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 64 tps: 765.30 qps: 765.30 (r/w/o: 0.00/765.30/0.00) lat (ms,95%): 102.97 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 64 tps: 769.20 qps: 769.20 (r/w/o: 0.00/769.20/0.00) lat (ms,95%): 102.97 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 64 tps: 772.39 qps: 772.39 (r/w/o: 0.00/772.39/0.00) lat (ms,95%): 101.13 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 64 tps: 771.91 qps: 771.91 (r/w/o: 0.00/771.91/0.00) lat (ms,95%): 101.13 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           76880
        other:                           0
        total:                           76880
    transactions:                        76880  (767.74 per sec.)
    queries:                             76880  (767.74 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.1370s
    total number of events:              76880

Latency (ms):
         min:                                   48.70
         avg:                                   83.27
         max:                                  676.55
         95th percentile:                      101.13
         sum:                              6402067.34

Threads fairness:
    events (avg/stddev):           1201.2500/10.45
    execution time (avg/stddev):   100.0323/0.02
```

### Threads = 72

```shell

```

### Threads = 80

```shell

```

### Threads = 128

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=128
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 128
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 128 tps: 1402.30 qps: 1402.30 (r/w/o: 0.00/1402.30/0.00) lat (ms,95%): 116.80 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 128 tps: 1434.15 qps: 1434.15 (r/w/o: 0.00/1434.15/0.00) lat (ms,95%): 108.68 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 128 tps: 1440.50 qps: 1440.50 (r/w/o: 0.00/1440.50/0.00) lat (ms,95%): 108.68 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 128 tps: 1365.39 qps: 1365.39 (r/w/o: 0.00/1365.39/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 128 tps: 1353.99 qps: 1353.99 (r/w/o: 0.00/1353.99/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 128 tps: 1340.21 qps: 1340.21 (r/w/o: 0.00/1340.21/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 128 tps: 1371.21 qps: 1371.21 (r/w/o: 0.00/1371.21/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 128 tps: 1354.50 qps: 1354.50 (r/w/o: 0.00/1354.50/0.00) lat (ms,95%): 121.08 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 128 tps: 1314.79 qps: 1314.79 (r/w/o: 0.00/1314.79/0.00) lat (ms,95%): 125.52 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 128 tps: 1361.21 qps: 1361.21 (r/w/o: 0.00/1361.21/0.00) lat (ms,95%): 123.28 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           137513
        other:                           0
        total:                           137513
    transactions:                        137513 (1371.09 per sec.)
    queries:                             137513 (1371.09 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.2930s
    total number of events:              137513

Latency (ms):
         min:                                   49.00
         avg:                                   93.12
         max:                                  881.66
         95th percentile:                      121.08
         sum:                             12805088.68

Threads fairness:
    events (avg/stddev):           1074.3203/12.48
    execution time (avg/stddev):   100.0398/0.04
```

### Threads = 256

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=256
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 256
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 256 tps: 2576.60 qps: 2576.60 (r/w/o: 0.00/2576.60/0.00) lat (ms,95%): 132.49 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 256 tps: 2594.49 qps: 2594.49 (r/w/o: 0.00/2594.49/0.00) lat (ms,95%): 132.49 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 256 tps: 2613.53 qps: 2613.53 (r/w/o: 0.00/2613.53/0.00) lat (ms,95%): 132.49 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 256 tps: 2595.89 qps: 2595.89 (r/w/o: 0.00/2595.89/0.00) lat (ms,95%): 134.90 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 256 tps: 2554.57 qps: 2554.57 (r/w/o: 0.00/2554.57/0.00) lat (ms,95%): 132.49 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 256 tps: 2554.13 qps: 2554.13 (r/w/o: 0.00/2554.13/0.00) lat (ms,95%): 137.35 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 256 tps: 2542.08 qps: 2542.08 (r/w/o: 0.00/2542.08/0.00) lat (ms,95%): 137.35 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 256 tps: 2586.09 qps: 2586.09 (r/w/o: 0.00/2586.09/0.00) lat (ms,95%): 132.49 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 256 tps: 2144.08 qps: 2144.08 (r/w/o: 0.00/2144.08/0.00) lat (ms,95%): 219.36 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 256 tps: 2500.65 qps: 2500.65 (r/w/o: 0.00/2500.65/0.00) lat (ms,95%): 142.39 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           252882
        other:                           0
        total:                           252882
    transactions:                        252882 (2519.89 per sec.)
    queries:                             252882 (2519.89 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.3528s
    total number of events:              252882

Latency (ms):
         min:                                   47.20
         avg:                                  101.30
         max:                                 1549.25
         95th percentile:                      144.97
         sum:                             25615832.13

Threads fairness:
    events (avg/stddev):           987.8203/16.00
    execution time (avg/stddev):   100.0618/0.06
```

### Threads = 512

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=512
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 512
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 512 tps: 4444.32 qps: 4444.32 (r/w/o: 0.00/4444.32/0.00) lat (ms,95%): 215.44 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 512 tps: 3905.25 qps: 3905.25 (r/w/o: 0.00/3905.25/0.00) lat (ms,95%): 350.33 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 512 tps: 4266.86 qps: 4266.86 (r/w/o: 0.00/4266.86/0.00) lat (ms,95%): 240.02 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 512 tps: 4444.85 qps: 4444.85 (r/w/o: 0.00/4444.85/0.00) lat (ms,95%): 244.38 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 512 tps: 4266.00 qps: 4266.00 (r/w/o: 0.00/4266.00/0.00) lat (ms,95%): 248.83 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 512 tps: 4465.87 qps: 4465.87 (r/w/o: 0.00/4465.87/0.00) lat (ms,95%): 235.74 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 512 tps: 4405.11 qps: 4405.11 (r/w/o: 0.00/4405.11/0.00) lat (ms,95%): 253.35 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 512 tps: 4475.55 qps: 4475.55 (r/w/o: 0.00/4475.55/0.00) lat (ms,95%): 244.38 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 512 tps: 4231.34 qps: 4231.34 (r/w/o: 0.00/4231.34/0.00) lat (ms,95%): 262.64 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 512 tps: 4431.73 qps: 4431.73 (r/w/o: 0.00/4431.73/0.00) lat (ms,95%): 240.02 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           433896
        other:                           0
        total:                           433896
    transactions:                        433896 (4318.67 per sec.)
    queries:                             433896 (4318.67 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          100.4682s
    total number of events:              433896

Latency (ms):
         min:                                   49.39
         avg:                                  118.09
         max:                                 2939.08
         95th percentile:                      277.21
         sum:                             51240620.19

Threads fairness:
    events (avg/stddev):           847.4531/20.46
    execution time (avg/stddev):   100.0793/0.08
```

```

```

### Threads = 600

```shell
sysbench oltp_update_index run --config-file=config --tables=32 --table-size=10000 --threads=600
sysbench 1.0.20 (using bundled LuaJIT 2.1.0-beta2)

Running the test with following options:
Number of threads: 600
Report intermediate results every 10 second(s)
Initializing random number generator from current time


Initializing worker threads...

Threads started!

[ 10s ] thds: 600 tps: 4896.11 qps: 4896.11 (r/w/o: 0.00/4896.11/0.00) lat (ms,95%): 356.70 err/s: 0.00 reconn/s: 0.00
[ 20s ] thds: 600 tps: 4957.00 qps: 4957.00 (r/w/o: 0.00/4957.00/0.00) lat (ms,95%): 369.77 err/s: 0.00 reconn/s: 0.00
[ 30s ] thds: 600 tps: 4999.46 qps: 4999.46 (r/w/o: 0.00/4999.46/0.00) lat (ms,95%): 369.77 err/s: 0.00 reconn/s: 0.00
[ 40s ] thds: 600 tps: 4920.89 qps: 4920.89 (r/w/o: 0.00/4920.89/0.00) lat (ms,95%): 376.49 err/s: 0.00 reconn/s: 0.00
[ 50s ] thds: 600 tps: 4782.17 qps: 4782.17 (r/w/o: 0.00/4782.17/0.00) lat (ms,95%): 369.77 err/s: 0.00 reconn/s: 0.00
[ 60s ] thds: 600 tps: 4797.93 qps: 4797.93 (r/w/o: 0.00/4797.93/0.00) lat (ms,95%): 376.49 err/s: 0.00 reconn/s: 0.00
[ 70s ] thds: 600 tps: 4776.86 qps: 4776.86 (r/w/o: 0.00/4776.86/0.00) lat (ms,95%): 369.77 err/s: 0.00 reconn/s: 0.00
[ 80s ] thds: 600 tps: 4931.54 qps: 4931.54 (r/w/o: 0.00/4931.54/0.00) lat (ms,95%): 369.77 err/s: 0.00 reconn/s: 0.00
[ 90s ] thds: 600 tps: 4953.58 qps: 4953.58 (r/w/o: 0.00/4953.58/0.00) lat (ms,95%): 363.18 err/s: 0.00 reconn/s: 0.00
[ 100s ] thds: 600 tps: 4947.71 qps: 4947.71 (r/w/o: 0.00/4947.71/0.00) lat (ms,95%): 363.18 err/s: 0.00 reconn/s: 0.00
SQL statistics:
    queries performed:
        read:                            0
        write:                           490244
        other:                           0
        total:                           490244
    transactions:                        490244 (4847.60 per sec.)
    queries:                             490244 (4847.60 per sec.)
    ignored errors:                      0      (0.00 per sec.)
    reconnects:                          0      (0.00 per sec.)

General statistics:
    total time:                          101.1297s
    total number of events:              490244

Latency (ms):
         min:                                   50.20
         avg:                                  122.51
         max:                                 4084.86
         95th percentile:                      369.77
         sum:                             60058725.30

Threads fairness:
    events (avg/stddev):           817.0733/22.07
    execution time (avg/stddev):   100.0979/0.13

```

### Threads = 800

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
