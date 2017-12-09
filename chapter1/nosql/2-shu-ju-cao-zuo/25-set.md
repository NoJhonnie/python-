## set

* 无序集合
* 元素为string类型
* 元素唯一性，不重复

### 命令

#### 设置

添加元素

```
SADD key member [member...]
```

#### 获取

1.获取key集合的所有元素

```
SMEMBERS key
```

2.返回集合元素个数

```
SCARD key
```

#### 其他

1.求多个集合交集

```
SINTER key [key...]
```

2.求某集合与其他集合的差集

```
SDIFF key [key...]
```

3.多个集合的合集

```
SUNION key [key...]
```

4.元素是否在集合中

```
SISMEMBER key member
```



