## 键命令

1.查找键，参数可以正则

```
KEYS pattern
```

2.判断键是否存在，如果存在返回1，不存在返回0

```
EXISTS key [key...]
```

3.查看键对应的value类型

```
TYPE key
```

4.删除键及对应的值

```
DEL key [key...]
```

5.设置过期时间，单位为秒，没有设置过期时间，则一直存在直到DEL移除

```
EXPIRE key seconds
```

6.查看有效时间，单位为秒

```
TTL key
```

