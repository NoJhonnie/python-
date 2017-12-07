### 插入

```
db.集合名称.insert(document)
```

插入文档时，如果不指定\_id时，则会自动分配一个ObjectID

```
db.stu.insert({name:'gj',gender:1})
```

```
s1={_id:'20148045',name:'hr'}
s1.gender=0
db.stu.insert(s1)
```

### 简单查询

```
db.集合名称.find()
```

### 更新

```
db.集合名称.update(
    <query>,    查询条件，sql类比where
    <update>,    更新操作符，sql类比set
    {multi:<boolean>    默认false，表示只更新找到的第一条记录；
                        true表示满足条件的文档全部更新
}
```

```
db.stu.update({name:'hr'},{name:'mnc'})    全文档更新
```

```
db.stu.insert({name:'hr',gender:0})
db.stu.update({name:'hr'},{$set:{name:'hys'}})    指定属性更新$set
```

```
db.stu.update({},{$set:{gender:0}},{multi:ture})    匹配多数据
```

### 保存

```
db.集合.save(document)
```

* 文档id存在则修改，\_id不存在则添加

```
db.stu.save({_id:'20148045','name':'yk',gender:1})
```

### 删除

```
db.集合.remove(
<query>,    可选，删除文档的条件
{justOne:<boolean>}    可选默认false删除多条；true只删一条
)
```

```
db.stu.remove({gender:0},{justOne:true})
```

```
db.stu.remove({})
```



