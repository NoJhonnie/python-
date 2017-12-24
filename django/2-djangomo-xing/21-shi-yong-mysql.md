## MySQL数据库配置

在虚拟环境中安装mysql包

```
pip install mysql-python
```

在mysql中创建数据库

```
create databases test1 charset=utf8
```

修改settings.py文件中的DATABASES选项

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'test2',
        'USER': '用户名',
        'PASSWORD': '密码',
        'HOST': '数据库服务器ip，本地可以使用localhost',
        'PORT': '端口，默认为3306',
    }
}
```

#### 使用数据库生成模型类

```
python manage.py inspectdb > booktest/models.py
```



