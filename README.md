# 使用docker搭建PHP开发环境

## 目录和文件说明

- apps 自定义的应用镜像目录
- config 本地的一些自定义配置
- data 数据目录，用来存放持久化的数据，如 mysql 的数据文件
- htdocs web程序代码目录
- logs 日志目录，用来保存 nginx、php 等应用产生的日志

## 安装

docker安装见https://www.docker.com/products/overview

## 启动

进入项目目录develop。

前台运行：

```bash
$ docker-compose up
```

后台运行：

```bash
$ docker-compose up -d
```

关闭：

```bash
$ docker-compose down
```

## xdebug配置

由于在容器里面无法直接获取到宿主机的IP地址。因此在如果要使用xdebug调试的话需要配置在宿主机（物理机）上配置一个名为`XDEBUG_HOST`的环境变量，docker-compose在启动时将读取这个变量并写入到容器中的xdebug配置文件里：

```bash
$ export XDEBUG_HOST=192.168.1.2
```
