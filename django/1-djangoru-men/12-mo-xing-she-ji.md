## 模型设计

图书表结构设计

* 表名：BookInfo
* 图书名称：btitle
* 图书发布时间：bpub\_date

英雄表结构设计：

* 表名：HeroInfo
* 英雄姓名：hname
* 影响性别：hgender
* 英雄简介：hcontent
* 所属图书：hbook

图书-英雄的关系：一对多

### 数据库配置

settings.py文件中，通过DATABASES进行数据库设置

django数据库：sqlite、mysql等

django默认为sqlite数据库

### 应用创建

创建应用命令

```
python manage.py startapp test1
```

### 定义模型类

一个数据表就要有一个模型类对应

打开models.py定义模型类

引入包from django.db import models

模型类继承models.Model类

输出对象时调用str方法

注：不需要定义主键，生成时会自动添加

### 生成数据表

激活模型：编辑settings.py，将test1应用加入到installed\_apps中

生成迁移文件：根据模型类生成sql语句

```
python manage.py makemigrations
```

迁移文件被生成到应用的migrations中

执行迁移：执行sql语句生成数据表

```
python manage.py migrate
```

### 测试数据操作

进入python shell，进行简单的模型API练习

```
python manage.py shell
```

* 引入需要的包：

```
from booktest.models import BookInfo,HeroInfo
from django.utils import timezone
from datetime import *
```

* 查询所有图书信息：

```
BookInfo.objects.all()
```

* 新建图书信息：

```
b = BookInfo()
b.btitle="射雕英雄传"
b.bpub_date=datetime(year=1990,month=1,day=10)
b.save()
```

* 查找图书信息：

```
b=BookInfo.objects.get(pk=1)
注：pk为主键
```

* 输出图书信息：

```
b
b.id
b.btitle
```

* 修改图书信息：

```
b.btitle=u"天龙八部"
b.save()
```

* 删除图书信息：

```
b.delete()
```



