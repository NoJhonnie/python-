## 主从配置

* 一个master可以有多个slave。一个slave又可以拥有多个slave，形成多级服务器集群架构

1.设置主服务器

```
bind 192.168.1.107
```

2.设置从服务器的配置，slaveof后面写主机ip，再写端口\(必须\)

```
bind 192.168.1.107
slaveof 192.168.1.11 6379
```

3.master和slave分别执行info命令，

4.master上写数据

```
set hello world
```

5.slave读数据

```
get hello
```

