### $limit

限制聚合管道返回的文档数

```
db.stu.aggregate([{$limit:2}])    查询2条学生信息
```

### $skip

跳过指定数量文档，返回剩下的文档

```
db.stu.aggregate([{$skip:2}])    跳过前面两条的学生信息
```

```
db.stu.aggregate([
    {$group:{_id:'$gender',counter:{$sum:1}}},
    {$sort:{counter:1}},
    {$skip:1},{$limit:1}
    ])    统计男女生人数，按人数升序，取第二条数据
```



