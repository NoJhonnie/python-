## 服务器

运行开启服务器

```
python manage.py runserver ip:port
注： 
1.默认端口为8000
2.开发阶段使用
3.输入127.0.0.0:8000打开默认页面
4.修改文件不需要重启服务器，增删文件则需要
5.ctrl+c停止服务器
```

## 管理操作

#### django管理

创建管理员用户

```
python manage.py createsuperuser
创建完以后可以通过127.0.0.1:8000/admin进行访问
```

#### 管理界面本地化

编辑settings.py文件，设置编码、时区

```
LANGUAGE_CODE = 'zh-Hans'
TIME_ZONE = 'Asia/Shanghai'
```

### admin注册booktest模型

打开booktest/admin.py文件，注册模型

```
from django.contrib import admin
from models import BookInfo
admin.site.register(BookInfo)
```

注：需要在str方法中添加”.encode\('utf-8'\)“避免出现ascii错误

### 自定义管理页面

Django提供了admin.ModelAdmin类，可以通过定义ModelAdmin的子类，来定义模型在Admin界面的显示方式

```
class QuestionAdmin(admin.ModelAdmin):
    ...
admin.site.register(Question,QuestionAdmin)
```

#### 列表页属性

显示字段，点击排序

```
list_display = ['pk', 'btitle', 'bpub_date']
```

过滤字段，过滤框在右侧

```
list_filter = ['btitle']
```

搜索字段，搜索框在上方

```
search_fields = ['btitle']
```

分页，分页框在下方

```
list_per_page = 10
```



