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

### 启动客户端

```
redis-cli
```



