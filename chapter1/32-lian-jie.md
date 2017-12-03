将三个表一起查询，使用连接查询

```
select students.sname,subjects.stitle,scores.score
from scores
inner join students on scores.stuid=students.id
inner join subjects on scores.subid=subjects.id;
```

连接查询分类：

* 表A inner join 表B：表A与表B匹配的出现在结果中；
* 表A left join 表B：表A与表B匹配的行为出现在结果中，外加表A中独有的数据，未对应的数据使用null填充；
* 表A right join 表B：表A与表B匹配的行为出现在结果中，外加表B中独有的数据，未对应的数据使用null填充。

条件查询用“表名.列名”

多个表中列名不重复可以省略“表名.”部分

表的名称太长，可以可以在表名后面使用‘as 简写名’或‘简写名’，未表起个临时的简写名称。

查询学生的姓名、平均分

```
select students.sname, avg(scores.score)
from scores 
inner join students on scores.stuid=students.id
group by students.sname;
```

查询男生的姓名和总分

```
select students.name,sum(scores.score)
from scores
inner join students on scores.stuid=students.id
where students.gender=1
gourp by students.sname;
```

查询科目名称和平均分

```
select scores.stitle,avg(scores.score)
from scores
inner join subjects on scores.subid=subjects.id
```

查询未删除科目的名称、最高分、平均分

```
select scores.stitle,max(scores.score),avg(scores.score)
from scores
inner join subject on scores.subid=subject.id
where subject.isdelete=0
group by subject.stitle;
```



