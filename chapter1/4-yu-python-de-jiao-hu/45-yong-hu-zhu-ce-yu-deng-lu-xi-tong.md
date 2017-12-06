### 创建用户表

表userinfos的结构如下：

* id
* uname
* upwd
* isdelete

需要对密码进行加密

md5加密，包含32个字符

sha1加密，包含40个字符

```
create table userinfos(
uid int primary key auto_increment,
uname varchar(20),
upwd char(40) default 123456789
isdelete bit default 0);
```

### 用户登陆

```
#encoding=utf-8
from MysqlHelper import MysqlHelper
from hashlib import sha1

sname = raw_input("please input your account:")
spwd = raw_input("please input your password:")

s1 = sha1()
s1.update(spwd)
spwdSha1 = s1.hexdigest()

sql = "select upwd from userinfos where uname=%s"
params = [sname]
sqlHelper = MysqlHelper('192.168.1.107',3306,'db_name','root','root')
upwd = sqlHelper.get_one(sql,params)

if upwd != None and upwd[0] == spwdSha1:
    print 'login in success!!!'

elif upwd != None and upwd[0] != spwdSha1:
    print 'Password Error!'
else:
    print 'no account!'
```

### 用户注册

```
#encoding=utf-8
from MysqlHelper import MysqlHelper
from hashlib import sha1

sname = raw_input("please input your account:")
spwd = raw_input("please input your password:")

s1 = sha1()
s1.update(spwd)
spwdSha1 = s1.hexdigest()

sql = "select upwd from userinfos where uname=%s"
params = [sname]
sqlHelper = MysqlHelper('192.168.1.107',3306,'db_name','root','root')
upwd = sqlHelper.get_one(sql,params)

if upwd != None and upwd[0] == spwdSha1:
    print 'login in success!!!'

elif upwd != None and upwd[0] != spwdSha1:
    print 'Password Error!'
else:
    print 'no account!'
```



