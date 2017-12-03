地区信息表的每种信息数量有限，建立新表需要存储区、乡镇信息，将多个信息表定在一个表中。

表areas，结构

* id
* atitle
* pid

没有所属的省份，可以填写null

城市所属的省份pid，填写省对应的编号id

结构不变可以添加区县、乡镇、社区等信息

创建语句

```
create table areas(
id int primary key,
atitle varchar(20),
pid int,
foreign key(id) references areas(id)
);
```



