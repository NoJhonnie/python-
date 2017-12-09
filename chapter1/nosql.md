# 简介

NoSQL全名Not Only SQL，是非关系型的数据库。是随着访问量的上升，网站的数据库性能出现问题，NoSQL被设计出来。

## 优点

* 高可扩展性
* 分布式计算
* 低成本
* 架构的灵活性，半结构化数据
* 没有复杂的关系

## 缺点

* 没有标准化
* 有限的查询功能
* 不直观的程序

## 分类

| 类型 | 代表 | 特点 |
| :---: | :---: | :---: |
| 列存储 | Hbase、Cassandra、Hypertable | 列存储数据、存储结构化和半结构化数据、方便数据压缩、少数查询有非常大的IO优势 |
| 文档存储 | MongoDB、CouchDB | 类似json格式存储文档型的、字段建立索引从而实现数据库的某些功能 |
| key-value存储 | TokyoCabinet、BerkeleyDB、MemcacheDB、Redis | 通过key快速查询value、value格式不限 |
| 图存储 | Neo4J、FlockDB | 方便图形关系 |
| 对象存储 | db4o、Versant | 类似面向对象语言的语法操作数据库，对象存储数据 |
| xml数据库 | Berkeley DB XML、BaseX | 存储XML数据，支持XML内部查询，如XQuery、Xpath |



