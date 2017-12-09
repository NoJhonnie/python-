## hash

hash存储对象，对象的格式为键值对

### 命令

#### 设置

1.设置单个属性

```
HSET key field value
```

2.设置多个属性

```
HMSET key field value [field value ... ]
```

#### 获取

1.获取一个属性的值

```
HGET key field
```

2.获取多个属性的值

```
HMGET key field [field ... ]
```

3.获取所有属性和值

```
HGETALL key
```

4.获取所有的属性

```
HKEYS key
```

5.返回包含属性的个数

```
HLEN key
```

6.获取所有值

```
HVALS key
```

#### 其他

1.判断属性是否存储

```
HEXISTS key field
```

2.删除属性及值

```
HDEL key field [field...]
```

3.返回值的字符串长度

```
HSTRLEN key field
```

