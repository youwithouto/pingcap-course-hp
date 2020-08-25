# Go TPC

## tpc-c

### 数据

```shell
./bin/go-tpc tpcc -H 10.240.0.10 -P 4000 -D tpcc --warehouses 8 prepare -T 8
```

### 测试

```shell
./bin/go-tpc tpcc -H 10.240.0.10 -P 4000 -D tpcc --warehouses 8 run --time 1m -T 4

[Current] DELIVERY - Takes(s): 9.1, Count: 9, TPM: 59.2, Sum(ms): 7074, Avg(ms): 786, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 9.6, Count: 80, TPM: 497.6, Sum(ms): 18812, Avg(ms): 235, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] ORDER_STATUS - Takes(s): 7.3, Count: 7, TPM: 57.6, Sum(ms): 98, Avg(ms): 14, 90th(ms): 24, 99th(ms): 24, 99.9th(ms): 24
[Current] PAYMENT - Takes(s): 9.8, Count: 64, TPM: 391.4, Sum(ms): 12395, Avg(ms): 193, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 8.9, Count: 10, TPM: 67.1, Sum(ms): 193, Avg(ms): 19, 90th(ms): 24, 99th(ms): 64, 99.9th(ms): 64
[Current] DELIVERY - Takes(s): 9.8, Count: 10, TPM: 61.3, Sum(ms): 7850, Avg(ms): 785, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 9.9, Count: 72, TPM: 435.8, Sum(ms): 16693, Avg(ms): 231, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] ORDER_STATUS - Takes(s): 8.2, Count: 13, TPM: 95.2, Sum(ms): 112, Avg(ms): 8, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] PAYMENT - Takes(s): 9.8, Count: 77, TPM: 469.1, Sum(ms): 15168, Avg(ms): 196, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 9.2, Count: 11, TPM: 71.9, Sum(ms): 136, Avg(ms): 12, 90th(ms): 12, 99th(ms): 32, 99.9th(ms): 32
[Current] DELIVERY - Takes(s): 9.8, Count: 9, TPM: 54.9, Sum(ms): 7005, Avg(ms): 778, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 9.7, Count: 79, TPM: 488.3, Sum(ms): 18706, Avg(ms): 236, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] ORDER_STATUS - Takes(s): 8.0, Count: 5, TPM: 37.3, Sum(ms): 44, Avg(ms): 8, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] PAYMENT - Takes(s): 9.9, Count: 75, TPM: 453.7, Sum(ms): 14680, Avg(ms): 195, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 8.1, Count: 8, TPM: 59.6, Sum(ms): 83, Avg(ms): 10, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] DELIVERY - Takes(s): 7.3, Count: 6, TPM: 49.2, Sum(ms): 4678, Avg(ms): 779, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 10.0, Count: 79, TPM: 475.1, Sum(ms): 18579, Avg(ms): 235, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] PAYMENT - Takes(s): 9.9, Count: 83, TPM: 501.7, Sum(ms): 16447, Avg(ms): 198, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 9.8, Count: 6, TPM: 36.9, Sum(ms): 61, Avg(ms): 10, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] DELIVERY - Takes(s): 9.7, Count: 12, TPM: 74.2, Sum(ms): 9227, Avg(ms): 768, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 9.7, Count: 68, TPM: 419.2, Sum(ms): 15755, Avg(ms): 231, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] ORDER_STATUS - Takes(s): 9.8, Count: 11, TPM: 67.1, Sum(ms): 110, Avg(ms): 10, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] PAYMENT - Takes(s): 9.9, Count: 76, TPM: 458.7, Sum(ms): 14866, Avg(ms): 195, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 2.6, Count: 9, TPM: 205.7, Sum(ms): 123, Avg(ms): 13, 90th(ms): 32, 99th(ms): 32, 99.9th(ms): 32
[Current] DELIVERY - Takes(s): 7.8, Count: 5, TPM: 38.5, Sum(ms): 3994, Avg(ms): 798, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Current] NEW_ORDER - Takes(s): 9.9, Count: 98, TPM: 592.0, Sum(ms): 23436, Avg(ms): 239, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Current] ORDER_STATUS - Takes(s): 8.8, Count: 7, TPM: 47.5, Sum(ms): 67, Avg(ms): 9, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
[Current] PAYMENT - Takes(s): 10.0, Count: 64, TPM: 385.0, Sum(ms): 12063, Avg(ms): 188, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Current] STOCK_LEVEL - Takes(s): 9.3, Count: 4, TPM: 25.8, Sum(ms): 45, Avg(ms): 11, 90th(ms): 12, 99th(ms): 12, 99.9th(ms): 12
Finished
[Summary] DELIVERY - Takes(s): 59.1, Count: 51, TPM: 51.7, Sum(ms): 39828, Avg(ms): 780, 90th(ms): 1000, 99th(ms): 1000, 99.9th(ms): 1000
[Summary] DELIVERY_ERR - Takes(s): 59.1, Count: 1, TPM: 1.0, Sum(ms): 469, Avg(ms): 469, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Summary] NEW_ORDER - Takes(s): 59.7, Count: 477, TPM: 479.7, Sum(ms): 112194, Avg(ms): 235, 90th(ms): 512, 99th(ms): 512, 99.9th(ms): 512
[Summary] NEW_ORDER_ERR - Takes(s): 59.7, Count: 2, TPM: 2.0, Sum(ms): 114, Avg(ms): 57, 90th(ms): 112, 99th(ms): 112, 99.9th(ms): 112
[Summary] ORDER_STATUS - Takes(s): 57.3, Count: 43, TPM: 45.0, Sum(ms): 431, Avg(ms): 10, 90th(ms): 16, 99th(ms): 24, 99.9th(ms): 24
[Summary] PAYMENT - Takes(s): 59.8, Count: 439, TPM: 440.3, Sum(ms): 85619, Avg(ms): 195, 90th(ms): 256, 99th(ms): 512, 99.9th(ms): 512
[Summary] STOCK_LEVEL - Takes(s): 59.0, Count: 48, TPM: 48.9, Sum(ms): 641, Avg(ms): 13, 90th(ms): 24, 99th(ms): 64, 99.9th(ms): 64
tpmC: 479.7
```

## tpc-h

### 数据

```shell
./bin/go-tpc tpch prepare -H 10.240.0.10 -P 4000 -D tpch --sf 4 --analyze
```

### 测试

```shell
./bin/go-tpc tpch run -H 10.240.0.10 -P 4000 -D tpch --sf 4

[Summary] Q1: 6.21s
[Summary] Q2: 1.57s
[Summary] Q3: 4.01s
[Summary] Q4: 1.64s
[Summary] Q5: 5.41s
[Summary] Q6: 2.52s
[Summary] Q7: 3.44s
[Summary] Q8: 3.05s
[Summary] Q9: 29.58s
[Summary] Q10: 2.97s
[Summary] Q11: 1.35s
[Summary] Q12: 3.15s
[Summary] Q13: 3.65s
[Summary] Q14: 2.87s
[Summary] Q15: 6.41s
[Summary] Q16: 1.67s
[Summary] Q17: 8.68s
[Summary] Q18: 20.22s
[Summary] Q19: 3.58s
[Summary] Q20: 2.47s
[Summary] Q21: 5.17s
[Summary] Q22: 1.97s

```
