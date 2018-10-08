# 分布式锁


## 设置锁

- 分布式锁目的是只允许一个客户端在当前使用，用完后通过del释放
```shell
> setnx lock:atom true

> do something

> del lock:atom
```

- 但如果执行过程中出现异常，锁未被释放就好陷入死锁，其他客户端将永远无法使用


## 设置过期时间

> 所以可以给锁加一个过期时间

```shell
> setnx lock:atom true

> expire lock:atom 5

> del lock:atom

```

> 但如果在 setnx 与 expire 之间 进程挂了或机器断电等因素，过期时间操作得不到执行，依然会陷入死锁

- 原因是 setnx和 expire是两条指令不是原子指令

## Redis 2.8 set指令加入了扩展参数

> setnx与expire可以一起执行解决了这个问题

```shell
> set lock:atom true ex 5 nx
>  do something
> del lock:atom
```

## 超时问题

## 可重入性

