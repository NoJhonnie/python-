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

## 表的创建

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



