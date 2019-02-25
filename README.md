# 使用 Docker 快速部署简易的 LNMP 环境

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
$ docker-compose up -d   // 容器编排命令
```