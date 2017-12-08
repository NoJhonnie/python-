用于过滤数据，标准查询操作

```
db.stu.aggregate([{$match:{age:{$gt:20}}}])    查询年龄大于20的学生
```

```
db.stu.aggregate([
    {$match:{age:{$gt:20}}},
    {$group:{_id:'$gender',counter:{$sum:1}}}
    ])        查询年龄大于20的男生、女生人数
```



