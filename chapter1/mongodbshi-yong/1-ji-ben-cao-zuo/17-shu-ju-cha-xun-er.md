### 方法

limit\(\)：**限定**读取指定数量的文档

```
db.集合.find().limit(number)    number表示获取的数量，默认全部
```

skip\(\)：跳过指定数量的文档

```
db.集合.find().skip(number)    number跳过记录条数，默认0
```

* 注：limit\(\)和skip\(\)可以一起使用

sort\(\):对结果**排序**

```
db.集合.find().sort({字段:1,...})    1为升序，-1为降序
```

count\(\):统计结果

```
db.集合.count(条件)
db.集合.find({条件}).count()
```

### 投影

将查询到的结果，选择性显示部分字段

```
db.集合.find({},{字段名:1,...})
```

注：需要显示的字段设置为1，不设置默认为不显示0
