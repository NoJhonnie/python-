## 视图

对于复杂的查询，多次使用是一件麻烦的事情，可以将查询封装起来，封装起来的即为视图。

## 事务

一个业务逻辑的多个sql语句，希望它要么全部执行成功，要么将操作退回，这时就要使用事务。

使用事务可以完成退回功能，保证业务逻辑的正确性。

事务四大特性\(简称ACID\)

* **原子性**\(Atomicity\)：事务中的全部操作在数据库中是不可分割的，要么全部完成，要么均不执行
* **一致性**\(Consistency\)：几个并行执行的事务，其执行结果必须与按某一顺序串行执行的结果相一致
* **隔离性**\(Isolation\)：事务的执行不受其他事务的干扰，事务执行的中间结果对其他事务必须是透明的
* **持久性**\(Durability\)：对于任意已提交事务，系统必须保证该事务对数据库的改变不被丢失，即使数据库出现故障

注意：表的类型必须时innodb或bdb类型

查看表的创建语句

```
show create table students;
```

修改表的类型

```
alter table '表名' engine=innodb;
```

事务语句

```
开启begin;
提交commit;
回滚rollback;
```


