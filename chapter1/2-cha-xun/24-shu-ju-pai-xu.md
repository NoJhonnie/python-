为了方便数据的查看，需要对数据进行排序

语法：

```
select * from 表名 where 条件 
order by 列1 asc|desc,列2 asc|desc...
```

* 排序顺序按照列1的值，接着是列2的值，以此类推
* 默认是从小到大的排列
* asc是从小到大的升序
* desc是从大到小的降序

例：

查询未删除男生的信息，按学号降序排序

```
select * from students 
where gender=1 and isdelete=0
order by id dasc;
```

查询未删除科目信息，按名称升序

```
select * from subject
where isdelete=0
order by stitle;
```



