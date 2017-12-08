### $sort

对文档进行排序输出

```
db.stu.aggregate([{$sort:{age:1}}])    查询学生信息
```

```
db.stu.aggregate([
    {$group:{_id:'$gender',counter:{$sum:1}}},
    {$sort:{counter:-1}}
    ])    查询男女生人数，按人数降序
```



