### 基本操作

* MongoDB将数据存储为一个文档，数据结构由键值对组成
* MongoDB文档类似JSON对象，字段值可以包含其他文档、数组、文档数组
* 安装管理mongodb环境
* 完成数据库、集合的管理
* 数据的增加、修改、删除、查询

### SQL和MongoDB名词

| SQL术语 | MongoDB术语 | 解释/说明 |
| :--- | :--- | :--- |
| database | database | 数据库 |
| table | collection | 数据库表/集合 |
| row | document | 数据记录行/文档 |
| column | field | 数据字段/域 |
| index | index | 索引 |
| table joins |  | 表连接/不支持 |
| primary key | primary key | 主键，MongoDB自动将\_id字段设置为主键 |

* MongoDB的三元素：数据库、集合、文档

1. 集合对应关系数据库中的表
2. 文档对应关系数据库中的行

* 文档，就是一个对象，由键值对构成，是json的扩展Bson形式

```
{'name':'guojing','gender':'男'}
```

* 集合：类似于关系数据库中的表，存储多个文档，结构不固定，如可以存储如下文档在一个集合中

```
{'name':'guojing','gender':'男'}
{'name':'huangrong','age':18}
{'book':'shuihuzhuan','heros':'108'}
```

* 数据库：是一个集合的物理容器，一个数据库中可以包含多个文档
* 一个服务器通常有多个数据库



