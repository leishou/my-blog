# Redis集群实战

参考博客：https://juejin.cn/post/7226710109585834040?searchId=20230808111451BEC5903EA2AB50798C64

https://juejin.cn/post/6844903670572646413 

```
集群用于分担写入压力 主从用于灾备和高可用以及分担读压力
```

http://c.biancheng.net/redis/aof.html  AOF持久化配置

```
redis-cli --cluster create 127.0.0.1:6379 127.0.0.1:6380 127.0.0.1:6381 127.0.0.1:6382 127.0.0.1:6383 127.0.0.1:6384 --cluster-replicas 1 -a 123456

作者：Neuronet
链接：https://juejin.cn/post/7226710109585834040
来源：稀土掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
```

```
redis-cli --cluster create 127.0.0.1:6379 127.0.0.1:6380 127.0.0.1:6381 127.0.0.1:6382 127.0.0.1:6383 127.0.0.1:6384 --cluster-replicas 1 -a 123456
```

```
redis-server.exe redis.windows.conf 启动节点
```

