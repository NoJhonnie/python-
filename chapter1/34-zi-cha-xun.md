嵌套查询

查询各学生的语文、数学、英语成绩

```
select sname,
(select sco.scores from scores sco 
inner join subjects sub on sco.subid=sub.id 
where sub.stitle='语文' and stuid=stu.id) as 语文，
(select sco.scores from scores sco 
inner join subjects sub on sco.subid=sub.id 
where sub.stitle='数学' and stuid=stu.id) as 数学，
(select sco.scores from scores sco 
inner join subjects sub on sco.subid=sub.id 
where sub.stitle='英语' and stuid=stu.id) as 英语
from students stu;
```



