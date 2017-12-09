## zset

* sorted set 有序的集合
* 元素为string类型
* 元素唯一性
* 每个元素关联double类型的score作为权重，通过权重将元素从小到大排序
* score可以相同

## 命令

#### 设置

添加

```
ZADD key score member [score member...]
```

#### 获取

返回指定范围内的元素

```
ZRANGE key start stop
```

返回元素个数

```
ZCARD key
```

返回有序集key，score在min和max之间

```
ZCOUNT key min max
```

返回有序集key，成员member的score值

```
ZSCORE key member
```



