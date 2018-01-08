##静态文件管理
静态文件即项目中的css、图片、js等部署在服务器上就没办法随不同情况而改变。
项目中的CSS、图片、js都是静态文件
###配置静态文件
在settings 文件中定义静态内容
```
STATIC_URL = '/static/'
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static'),
]
```
在项目根目录下创建static目录，再创建当前应用名称的目录
```
mysite/static/myapp/
```
在模板中可以使用硬编码
```
/static/my_app/myexample.jpg
```
在模板中可以使用static编码
```
{ % load static from staticfiles %}
<img src="{ % static "my_app/myexample.jpg" %}" alt="My image"/>
```