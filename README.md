# 使用 Docker 快速部署简易的 Ngixn + PHP + MySQL + Redis 环境

## 部署步骤

### 1、安装依赖工具

- Git  
- Docker [https://docs.docker.com/install/]
- Docker-compose [https://docs.docker.com/compose/install/#install-compose]

### 2、获取部署脚本

```
$ git clone https://github.com/JaderH/JadeDock.git
```

### 3、运行容器编排

```
$ cd /data/JadeDock   // 进入项目根目录
$ cp .env.example .env  // 配置相关选项
$ docker-compose up -d   // 容器编排命令
```

## 问题

### 1、编排后 MySQL 启动失败

```
$ docker logs Jade-mysql // 查看 MySQL 容器日志
```

如果出现 log 文件目录无法创建，请手动移除 `mysql/conf/my.cnf` 文件中关于日志部分的操作，要移除配置如下

```
slow_query_log=1
long_query_time=3
slow-query-log-file=/var/log/mysql/mysql.slow.log
log-error=/var/log/mysql/mysql.error.log
```

### 2、连接 MySQL 响应慢

在 `mysql/conf/my.cnf` 文件中增加如下配置

```
skip-name-resolve
```
