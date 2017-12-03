学生成绩表scores:

* id
* 学生
* 科目
* 成绩

学生成绩表是根据学生信息表和科目表两个综合出来的

语句

```
create scores(
id int primary key auto_increment,
stuid int,
suid int,
score decimal(5,2)
);
```

#### 外键

通过外键约束数据的同步性，对stuid添加外键约束

语句

```
alter table scores 
add constraint stu_sco foreign key(stuid)
references students(id);
```

所以一开始的创建语句为

```
create table scores(
id int primary key auto_increment,
stuid int,
subid int,
score decimal(5,2)
foreign key(stuid) references students(id)
foreign key(subid) references subjects(id)
);
```

#### 外键的级联操作

* 删除students表中数据的，而id值在scores存在，则会出现异常；
* 删除数据时，对应的也要逻辑删除；
* 创建表时指定级联操作，也可以创建表后再修改外键的级联操作

语法

```
alter table scores 
add constraint stu_sco foreign key(stuid)
references students(id) on delete cascade;
```

级联操作类型包括

* restrict\(限制\)：默认值，抛异常
* cascade\(级联\)：主表记录删掉，从表中的相关联的记录将被删除
* set null：将外键设置为空
* no action：什么都不做



