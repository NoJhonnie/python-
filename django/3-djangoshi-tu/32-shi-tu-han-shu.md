## 视图

视图本质是一个函数，它的参数有：HttpRequest实例、正则捕获的位置参数和捕获的关键字参数。在django的应用目录下views.py用于定义视图函数，但如果处理功能过多，可以定义到不同的py文件中。

```
新建views1.py
#coding:utf-8
from django.http import HttpResponse
def index(request):
    return HttpResponse("你好")

在urls.py中修改配置
from . import views1
url(r'^$', views1.index, name='index'),
```

### 错误视图

django自带几个默认的视图用于处理HTTP错误，如404视图等。

#### 404\(page not found\)视图

defaults.page\_not\_found\(request,template\_name='404.html'\)，同时默认的404视图将传递一个变量给模板：request\_path。如果django在检测URLconf的正则没有找到内容时将调用404视图。需要在settings中的DEBUG设置为True，同时在templates创建404.html。

```
DEBUG = False
ALLOWED_HOSTS = ['*', ]
```

#### 500 \(server error\) 视图 {#500-server-error-视图}

* defaults.server\_error\(request, template\_name='500.html'\)
* 在视图代码中出现运行时错误
* 默认的500视图不会传递变量给500.html模板
* 如果在settings中DEBUG设置为True，那么将永远不会调用505视图，而是显示URLconf 并带有一些调试信息

#### 400 \(bad request\) 视图 {#400-bad-request-视图}

* defaults.bad\_request\(request, template\_name='400.html'\)
* 错误来自客户端的操作
* 当用户进行的操作在安全方面可疑的时候，例如篡改会话cookie



