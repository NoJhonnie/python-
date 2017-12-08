#### $group

* 文档分组，统计结果

* \_id表示分组的依据，某个字段的格式为'$字段'

```
db.stu.aggregate([{$group:{_id:'$gender',counter:{$sum:1}}}])
```

#### Group by null

* 集合中所有文档为一组

```
db.stu.aggregate([{$group:{_id:null,counter:{$sum:1},avgAge:{$avg:'$age'}}}])
```

### 透视数据

```
db.stu.aggregate([{$group:{_id:'$gender',name:{$push:'$name'}}}])
```

使用$$ROOT将文档内容加入到结果集中的数组

```
db.stu.aggregate([{$group:{_id:'$gender',name:{$push:'$$ROOT'}}}])
```



