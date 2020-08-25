# go-ycsb

## 数据

```shell
./bin/go-ycsb load mysql -P workloads/workloada -p recordcount=10000 -p mysql.host=10.240.0.10 -p mysql.port=4000 --threads 16

***************** properties *****************
"mysql.host"="10.240.0.10"
"readallfields"="true"
"scanproportion"="0"
"dotransactions"="false"
"mysql.port"="4000"
"updateproportion"="0.5"
"operationcount"="1000"
"recordcount"="10000"
"workload"="core"
"insertproportion"="0"
"threadcount"="16"
"readproportion"="0.5"
"requestdistribution"="uniform"
**********************************************
INSERT - Takes(s): 9.9, Count: 3983, OPS: 403.1, Avg(us): 40073, Min(us): 31248, Max(us): 119453, 99th(us): 55000, 99.9th(us): 119000, 99.99th(us): 120000
INSERT - Takes(s): 19.9, Count: 8462, OPS: 425.6, Avg(us): 37724, Min(us): 28143, Max(us): 119453, 99th(us): 53000, 99.9th(us): 118000, 99.99th(us): 120000
INSERT - Takes(s): 29.9, Count: 9999, OPS: 334.6, Avg(us): 37353, Min(us): 28143, Max(us): 119453, 99th(us): 52000, 99.9th(us): 118000, 99.99th(us): 120000
INSERT - Takes(s): 39.9, Count: 9999, OPS: 250.7, Avg(us): 37353, Min(us): 28143, Max(us): 119453, 99th(us): 52000, 99.9th(us): 118000, 99.99th(us): 120000
INSERT - Takes(s): 49.9, Count: 9999, OPS: 200.5, Avg(us): 37353, Min(us): 28143, Max(us): 119453, 99th(us): 52000, 99.9th(us): 118000, 99.99th(us): 120000
INSERT - Takes(s): 59.9, Count: 9999, OPS: 167.0, Avg(us): 37353, Min(us): 28143, Max(us): 119453, 99th(us): 52000, 99.9th(us): 118000, 99.99th(us): 120000
Run finished, takes 1m7.487976269s
INSERT - Takes(s): 67.4, Count: 9999, OPS: 148.4, Avg(us): 37353, Min(us): 28143, Max(us): 119453, 99th(us): 52000, 99.9th(us): 118000, 99.99th(us): 120000
```

## 测试

```shell
./bin/go-ycsb run mysql -P workloads/workloada -p recordcount=10000 -p mysql.host=10.240.0.10 -p mysql.port=4000 --threads 16

***************** properties *****************
"operationcount"="1000"
"mysql.host"="10.240.0.10"
"insertproportion"="0"
"readproportion"="0.5"
"workload"="core"
"dotransactions"="true"
"scanproportion"="0"
"requestdistribution"="uniform"
"recordcount"="10000"
"mysql.port"="4000"
"readallfields"="true"
"updateproportion"="0.5"
"threadcount"="16"
**********************************************
Run finished, takes 1.699731297s
READ   - Takes(s): 1.7, Count: 488, OPS: 287.9, Avg(us): 2024, Min(us): 1368, Max(us): 26694, 99th(us): 4000, 99.9th(us): 27000, 99.99th(us): 27000
UPDATE - Takes(s): 1.7, Count: 504, OPS: 305.2, Avg(us): 43525, Min(us): 24609, Max(us): 118432, 99th(us): 54000, 99.9th(us): 119000, 99.99th(us): 119000
```
