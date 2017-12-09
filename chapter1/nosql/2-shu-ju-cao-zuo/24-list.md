## list

* 列表的元素类型string
* 按插入顺序排序
* 在列表的头部或尾部添加元素

## 命令

#### 设置

1.在头部插入数据

```
LPUSH key value [value...]
```

2.在尾部插入数据

```
RPUSH key value [value...]
```

3.在一个元素的前或后插入新元素

```
LINSERT key BEFORE|AFTER pivot value
```

4.设置指定索引的元素值，以0为基准，可以为负数，从尾部开始倒数

```
LSET key index value
```

#### 获取

1.移除并返回key对应的list的第一个元素

```
LPOP key
```

2.移除并返回存于key的list最后一个元素

```
RPOP key
```

3.返回key的列表里指定范围内的元素，start和end偏移量都是基于0的下标，可以为负数，与索引值类似

```
LRANGE key start stop
```

#### 其他

1.裁剪列表，改为原集合的一个子集start和end偏移量都是基于0的下标，可以为负数，与索引值类似

```
LTRIM key start stop
```

2.返回存储在key里的list长度

```
LLEN key
```

3.返回列表索引里的元素

```
LINDEX key index
```

