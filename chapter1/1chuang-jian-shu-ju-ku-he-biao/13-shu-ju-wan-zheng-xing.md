## 数据完整性

一个数据库就是一个完整的业务单元，可以含有多张表，相应的数据存储在表中。为了能让存储的数据更加准确，保证有效性，我们需要为表添加一些强制性的验证，包括数据字段的类型、约束。

## 字段类型

mysql的数据主要有以下几种：

* 数字：int、decimal
* 字符串：varchar、text
* 日期：datetime
* 布尔：bit

## 约束

主要有以下几个约束：

主键：primary key

非空：not null

唯一：unique

默认：default

外键：foreign key



