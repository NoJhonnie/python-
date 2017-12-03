按照字段分组，将字段相同的数据放到一个组中。可以对分组后的数据进行统计，进行聚合查询。分组能查询出相同的数据列，对于有差异的数据列则无法出现在结果中。

## 分组

语法：

```
select 列1，列2，聚合...from 表名 group by 列1，列2，列3...
```

查询男女总数

```
select gender as 性别，count(*) from students group by gender;
```

查询城市人口

```
select hometown as 家乡,count(*) from students group by hometown;
```

## 分组后数据筛选

语法：

```
select 列1，列2，聚合... from 表名 
group by 列1，列2... 
having 列1...聚合...
```

注：having后面的条件运算符与where相同

查询男生总数

```
方案一
select count(*) 
from students 
where gender=1;
方案二
select gender as 性别，count(*) 
from students 
group by gender
having gender=1;
```

对比where与having的区别

* where是对from后的表进行数据筛选的，属于原始数据的筛选
* having是对group by的结果进行筛选的



