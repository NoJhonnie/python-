## 使用命令连接

```
mysql -u 用户名 -p
输入密码
```

## 退出登陆

```
quit
```

## 查看版本

```
select version();
```

## 远程连接

```
mysql -hip地址 -uroot -p
```

* -h:ip地址为主机的IP地址
* -u:root为数据库用户名
* -p:为密码

# 数据库操作

* ## 查询所有的数据库

```
mysql> show databases;
```

查询的结果：

```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| python2            |
| sys                |
+--------------------+
```

* ## 创建数据库

```
mysql> create database db_name;
mysql> create database db_name default character set utf8; 默认字符集
```

* ## 查看数据库信息

```
mysql> show create schema db_name;
```

* ## 删除数据库

```
mysql> drop database db_name;
```

# 表的操作

要进行表的操作，先进入表所在的数据库。

```
use db_name;
```

* ## 表的创建

```
create table table_name(字段1 类型，字段2 类型 ， … ) ;
```

例子：

```
mysql> create table student(
    -> sid int,
    -> sname varchar(20),
    -> sage int
    -> );
```

表的创建还可以添加约束（非空、主键、外键、唯一、自增长、默认等），设置默认引擎，默认字符集，如下示例：

```
CREATE TABLE 'db' (
  'id' int primary key,
  'db' double DEFAULT NULL,
  'dm' decimal(10,0) DEFAULT NULL,
  'gender' int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8 ;
```

查看创建的表

```
mysql> desc student;
```

结果：

```
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| sid   | int(11)     | YES  |     | NULL    |       |
| sname | varchar(20) | YES  |     | NULL    |       |
| sage  | int(11)     | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```

* ## 查看表的结构和查看所有表

```
describe table_name;
show create table table_name;
```

查看所有表

```
show tables;
```

结果：

```
+-------------------+
| Tables_in_db_name |
+-------------------+
| student           |
+-------------------+
1 row in set (0.01 sec)
```

* ## 删除表

```
drop table table_name;
```

* ## 修改表

##### 修改表名

```
alter table old_table_name rename to new_table_name;
```

##### 添加字段

```
alter table table_name add column field_name varchar(50);
alter table table_name add column field_name varchar(50) first;添加到第一个位置
alter table table_name add column field_name varchar(50) after id;添加到id后面
```

##### 修改字段类型

```
alter table table_name modify column name text;
```

##### 修改字段名称

```
alter table table_name change column db dl double ;
```

将table\_name的db字段改名为dl字段，类型为double。

##### 删除字段

```
alter table table-name drop dm;
```

# 数据的增删改查

* ## 插入数据

##### 插入所有字段

```
insert into table_name values(1, 'mike', )
```

##### 部分插入

```
insert into table_name(name, age, gender) values('Jim', 18, 'male');
```

* ## 更新数据

##### 修改所有字段数据

```
update table_name set gender = 'male';
```

##### 带条件修改

```
update table_name set gender= 'female' where id=2;
```

##### 修改多个字段，用分号隔开。语法：set 字段名=值，字段名=值，...

```
update table_name set gender= 'female', name='Jack' where id=2;
```

* ## 删除数据

##### 删除所有数据delete

不建议用，除非特殊需要

```
delete from table_name;
```

##### 带条件删除delete

```
delete from table_name where id=2;
```

##### 使用truncate删除

```
truncate table table_name;
```

注：truncate不可带条件删除

##### delete和truncate的比较

| delete | trunate |
| :---: | :---: |
| 可以全表删除 | 可以全表删除 |
| 可以带条件删除 | 不可带条件删 |
| 不能删除表的约束 | 可以删除表的约束 |
| 删除数据可以回滚 | 删除的数据不能回滚 |

* ## 查询数据

##### 查询所有的字段

```
select * from table_name
```



