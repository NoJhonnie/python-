聚合函数是为了能快速计算出数据个数的函数。为了统计数据，mysql共提供了5个聚合函数。

##### count\(\*\)计算总行数，括号中‘\*’与列名，其结果是相同的

例：查询学生总数

```
select count(*) from students;
```

##### max\(列名\)求列的最大值

例：查询女生的编号最大值

```
select max(id) from students where gender=0;
```

##### min\(列名\)求列的最小值

例：查询未删除的学生最小编号

```
select min(id) from students where isdelete=0;
```

##### sum\(列名\)求列的总和

例：查询学生的编号总和

```
select sum(id) from students where gender=1;
```

##### avg\(列名\)表示列的平均值

例：查询未删除女生的编号平均值

```
select avg(id) from students where isdelete=0 and gender=0;
```



