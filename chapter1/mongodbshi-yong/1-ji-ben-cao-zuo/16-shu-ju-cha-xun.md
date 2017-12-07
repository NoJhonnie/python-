## 数据查询

### 基本查询

* find\(\):查询

```
db.集合.find({条件文档})
```

* findOne\(\):查询一个

```
db.集合.findOne({条件文档})
```

* 方法pretty\(\):将结果格式化

```
db.集合.find({条件文档}).pretty()
```

### 比较运算符

* 等于，默认
* 小于$lt
* 小于或等于$lte
* 大于$gt
* 大于或等于$gte
* 不等于$ne

### 逻辑运算符

* 逻辑与，默认
* 逻辑或$or

```
db.sub.find({$or:[{count:{$gte:10}}],title:"vb"})
```

### 范围运算符

* $in：某个范围内

```
db.sub.find({count:{$in:[5,10]}})
```

### 正则表达式

使用//或$regex正则表达式

```
db.sub.find({name:/^林/})
db.sub.find({name:{$regex:'^黄'}})
```

### 自定义查询

$where后面接函数，返回满足条件的数据

```
db.stu.find({$where:function(){return this.age>20}})
```



