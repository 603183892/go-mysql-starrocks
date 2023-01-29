## mysql 同步到 starrocks

![LICENSE](https://img.shields.io/badge/license-GPLv2%20-blue.svg)
![](https://img.shields.io/github/languages/top/liuxinwang/go-mysql-starrocks)
![](https://img.shields.io/badge/build-prerelease-brightgreen.svg)
[![Release](https://img.shields.io/github/release/liuxinwang/go-mysql-starrocks.svg?style=flat-square)](https://github.com/liuxinwang/go-mysql-starrocks/releases)


### 使用说明
#### 1. 修改配置文件
mysql-to-starrocks.toml
```toml
[mysql] # mysql连接信息
host = "127.0.0.1"
port = 3306
username = "root"
password = ""

[starrocks] # starrocks连接信息
host = "127.0.0.1"
port = 8040
username = "root"
password = ""

[[rule]] # 库表同步映射1
source-schema = "mysql_test"
source-table = "tb1"
target-schema = "starrocks_test"
target-table = "tb1"

[[rule]] # 库表同步映射2
source-schema = "mysql_test"
source-table = "tb2"
target-schema = "starrocks_test"
target-table = "tb2"
```
#### 2. 启动
```shell
[sr@ ~]$ ./go-mysql-starrocks-linux-xxxxxx -config mysql-to-starrocks.toml &
[sr@ ~]$ exit
```
#### 3. 查看日志
```shell
[sr@ ~]$ tail -f error.log
```

#### 4. 查看帮助
```shell
[sr@ ~]$ ./go-mysql-starrocks-linux-xxxxxx -h
```
