## string

* string是最基本的类型
* 最大存储512M数据
* string是二进制安全的，可以为任何数据：数字、图片、序列号对象等

### 命令

1.设置键值

```
set key value
```

2.设置键值及过期时间，单位为秒

```
SETEX key seconds value
```

3.设置多个键值

```
MSET key value [key value ...]
```

### 获取

1.根据键获取值，不存在则返回nil

```
GET key
```

2.根据多个键获取多个值

```
MGET key [key ... ]
```

### 运算

前提：值为数字

1.将key对应的value+1

```
INCR key
```

2.key对应的value加整数

```
INCRBY key increment
```

3.key对应的value-1

```
DECR key
```

4.key对应的value减整数

```
DECRBY key decrement
```

### 其他

1.追加值

```
APPEND key value
```

2.获取值长度

```
STRLEN key
```



