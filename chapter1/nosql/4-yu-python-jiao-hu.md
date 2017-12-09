### 安装

联网安装

```
pip install redis
```

### 交互代码

1.引入模块

```
import redis
```

2.连接

```
try:
    r=redis.StrictRedis(host='192.168.1.107', port=6379)
    print 'success!'
except Exception,e:
    print e.message
```

3.方式一：根据数据类型的不同，调用相应的方法，完成读写

```
r.set('name','hello')
name = r.get('name')
```

方式二：pipline。缓冲多条命令，一次性执行，减少服务器-客户端之间TCP数据库包，从而提高效率

```
pipe = r.pipeline()
pipe.set('name','world')
pipe.get('name')
pipe.execute()
```

### 封装

```
import redis
class RedisHelper():
    def __init__(self,host='192.168.1.107',port=6379):
        self._redis = redis.StrictRedis(host,port)
    def get(self,key):
        if self._redis.exists(key):
            return self._redis.get(key)
        else:
            return ""
    def set(self,key,value):
        self._redis.set(key,value)
```



