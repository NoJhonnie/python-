部分获取是在数据量过大时，数据一页中查看太过麻烦，其中最典型的就是分页

语法：

```
select * from 表名
where 条件
limit start，count
```

注：

* 从start开始，获取count条数据
* start索引从0开始

##### 分页

每页显示m条数据，当前显示第n页。该分页的逻辑为：

1. 查询总数据p1；
2. p1除以m得到p2；
3. p2为整数则总页数为p2，否则总页数为p2+1；

第n页的数据

```
select * from students
where isdelete=0
limit (n-1)*m,m
```



