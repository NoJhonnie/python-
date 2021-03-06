## 状态保持

http协议是无状态的，每次请求都是一次新的请求，不会记得之前通信的状态。同时客户端与服务器的一次通信就是一次会话。要实现状态保持的方式，可以通过存储与会话有关的数据来实现。存储数据方式包括：cookie和session，一般采用session对象。因为cookie保存在客户端，容易被人获取，而session将数据保存在服务器，而客户端存储session\_id。该方法的目的是为了在一段时间内跟踪请求者的状态，从而实现跨页面访问请求者的数据。注：不同的请求者之间不会共享这个数据，要与请求者一一对应。

### 启用session

在django创建项目时默认启用，在settings.py文件中

```
项INSTALLED_APPS列表中添加：
'django.contrib.sessions',

项MIDDLEWARE_CLASSES列表中添加：
'django.contrib.sessions.middleware.SessionMiddleware',
```

如果禁用会话，也就是删除上面两个值，则将节省一些性能消耗。

### 使用session

启用会话后，每个HttpRequest对象将具有一个session属性，它是一个类字典对象，它具有以下方法：

* get\(key, default=None\)：根据键获取会话的值
* clear\(\)：清除所有会话
* flush\(\)：删除当前的会话数据并删除会话的Cookie
* del request.session\['member\_id'\]：删除会话

### 会话过期时间

* set\_expiry\(value\)：设置会话的超时时间，如果没有指定，则两个星期后过期
* 如果value是一个整数，会话将在values秒没有活动后过期
* 若果value是一个imedelta对象，会话将在当前时间加上这个指定的日期/时间过期
* 如果value为0，那么用户会话的Cookie将在用户的浏览器关闭时过期
* 如果value为None，那么会话永不过期
* 修改视图中login\_handle函数，查看效果

### 存储session

存储会话方式使用settings.py的SESSION\_ENGINE项指定。有以下三种存储方式：

* 基于数据库的会话：这是django默认的会话存储方式，需要添加django.contrib.sessions到INSTALLED\_APPS设置中，运行manage.py migrate在数据库中安装会话表。

```
SESSION_ENGINE='django.contrib.sessions.backends.db'
```

* 基于缓存的会话：只存在本地中，如果丢失则不能找回，但比数据库的方式更快。

```
SESSION_ENGINE='django.contrib.sessions.backends.cache'
```

* 数据库和缓存同时使用：优先从本地缓存中获取，没有则从数据库中获取。

```
SESSION_ENGINE='django.contrib.sessions.backends.cached_db'
```

### 使用Redis缓存session

会话支持文件、纯cookie、Memcached、Redis等方式存储。以下是Redis存储。

* 安装包

```
pip install django-redis-sessions
```

* 修改settings中的配置，增加如下项

```
SESSION_ENGINE = 'redis_sessions.session'
SESSION_REDIS_HOST = 'localhost'
SESSION_REDIS_PORT = 6379
SESSION_REDIS_DB = 0
SESSION_REDIS_PASSWORD = ''
SESSION_REDIS_PREFIX = 'session'
```

* 管理redis的命令

```
启动：sudo redis-server /etc/redis/redis.conf
停止：sudo redis-server stop
重启：sudo redis-server restart
redis-cli：使用客户端连接服务器
keys *：查看所有的键
get name：获取指定键的值
del name：删除指定名称的键
```



