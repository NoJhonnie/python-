#### ubuntu安装

```
sudo apt-get install python-mysql
import Mysqldb
```

#### window10安装

下载MySQL-python-1.2.3.win-amd64-py2.7.exe文件

以管理员运行

```
import MySQLdb
```

### Connection对象

用于建立与数据库的连接，调用connect\(参数\)方法

* 参数host：连接的mysql主机，如果本机是'localhost'
* 参数port：连接的mysql主机的端口，默认是3306
* 参数db：数据库的名称
* 参数user：连接的用户名
* 参数password：连接的密码
* 参数charset：通信采用的编码方式，默认是'gb2312'，要求与数据库创建时指定的编码一致，否则中文会乱码

#### 对象方法

* close\(\)关闭连接
* commit\(\)事务提交，提交后才会生效
* rollback\(\)事务放弃，放弃之前的操作
* cursor\(\)返回Cursor对象，用于执行sql语句并获得结果

### Cursor对象

执行sql语句，该对象通过调用Connection对象的cursor\(\)方法

```
cursor1=conn.cursor()
```

#### 对象方法

* close\(\)关闭
* execute\(operation \[, parameters\]\)执行语句，返回受影响的行数
* fetchone\(\)执行查询语句，获取查询结果集的第一个行数据，以元组形式返回
* next\(\)执行查询语句时获取当前行的下一行
* fetchall\(\)执行查询时，获取结果集的所有行，每行构成一个元组，所有元组再组成一个元组
* scroll\(value \[,mode\]\)将行指针移动到某个位置

1. mode表示移动的方式
2. mode的默认值为relative，表示基于当前行移动到value，value为正则向下移动，value为负则向上移动
3. mode的值为absolute，表示基于第一条数据的位置，第一条数据的位置为0

#### 对象的属性

* rowcount只读属性，表示最近一次execute\(\)执行后影响的行数
* connection获取当前连接对象



