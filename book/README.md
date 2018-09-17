# Redis notes

## 什么是Redis

- 官网: https://redis.io/
- Github: https://github.com/antirez/redis
- redisdoc: http://redisdoc.com/

> Redis is an open source (BSD licensed)
> in-memory data structure store
> used as a database, cache and message broker

## 安装Redis

### 下载安装

```shell
wget http://download.redis.io/releases/redis-4.0.10.tar.gz
tar xzf redis-4.0.10.tar.gz
cd redis-4.0.10
make

# server
src/redis-server

# client
src/redis-cli
```

## Ubuntu

```shell
sudo apt-get update
sudo apt-get install redis-server
```

### Mac 安装

```shell
brew install redis
```

## 基本命令使用


## Redis编程

- 命令行使用
- 管道
- 发布订阅
- Lua脚本
- Lua脚本调试
- 内存优化
- 过期设置
- LRU缓存
- 事务
- 批量插入数据
- 分区
- 分布式锁
- Keyspace通知
- 创建二级索引

## Redis模块API

- 简介
- 实现原生数据类型
- 阻塞操作
- 模块API引用

## Redis使用场景

- 缓存
- 分布式锁


