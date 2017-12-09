## 安装

ubuntu

* 本地安装见onenote
* 在线安装

```
sudo apt-get update
sudo apt-get install redis-server
```

## 启动服务器

```
redis-server
```

### 端口

```
6379
```

### 远程访问

```
sudo vi /etc/redis/redis.conf
在127.0.0.1注释掉
```

### 客户端操作

```
redis-cli    启动客户端
ctr+c或quit    退出
```

apt-get安装的停止/启动/重启服务器

```
/etc/init.d/redis-server stop
/etc/init.d/redis-server start
/etc/init.d/redis-server restart
```



