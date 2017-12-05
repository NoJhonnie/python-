创建python文件，对学生表进行增删改操作

### 增加

```
#encoding=utf-8
import MySQLdb
try:
    conn = MySQLdb.connect(host='192.168.1.107', port='3306',
            db='db_name', user='root', passwd='root', charset='utf8')
    cncs = conn.cursor()
    count = cncs.execute("insert into students(sid, sname) values(3,'Gogh')")
    print count
    conn.commit()
    cncs.close()
    conn.close()
except Exception,e:
    print e.message
```

### 删除

```
#encoding=utf-8
import MySQLdb
try:
    conn = MySQLdb.connect(host='192.168.1.107', port='3306',
            db='db_name', user='root', passwd='root', charset='utf8')
    cncs = conn.cursor()
    count = cncs.execute("update students set sname='Cloud' where sid=1")
    cncs.close()
    conn.close()
except Exception,e:
    print e.message
```

## 修改

```
#encoding=utf-8
import MySQLdb
try:
    conn = MySQLdb.connect(host='192.168.1.107', port='3306',
            db='db_name', user='root', passwd='root', charset='utf8')
    cncs = conn.cursor()
    count = cncs.execute("delete from students where sid=3")
    print count
    conn.commit()
    cncs.close()
    conn.close()
except Exception,e:
    print e.message
```

### sql语句参数化

```
#encoding=utf-8
import MySQLdb
try:
    conn = MySQLdb.connect(host='192.168.1.107', port='3306',
            db='db_name', user='root', passwd='root', charset='utf8')
    cncs = conn.cursor()
    sname=raw_input("请输入学生姓名")
    params = [sname]
    count = cncs.execute('insert into students(sname) values(%s)', params)
    print count
    conn.commit()
    cncs.close()
    conn.close()
except Exception,e:
    print e.message
```



