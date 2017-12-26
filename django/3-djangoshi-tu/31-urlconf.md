## URLconf配置

在django中通过setttings.py的ROOT\_URLCONF来指定根级url的配置，urlpatterns是一个url\(\)实例的列表。一个url\(\)对象包括以下三个：

* 正则表达式
* 视图函数
* 名称name

在编写URLconf时需要注意：1.要在url中捕获一个值时，需要在它周围设置一对圆括号；2.不需要添加一个前导的反斜杠，如'test/'而不是‘/test/’；3.正则前面的r表示字符串不转义。特别需要注意请求的url会被看成一个普通的python字符串，而且匹配时不包括get或post请求的参数和域名。

```
http://www.itcast.cn/python/1/?i=1&p=new
只匹配“/python/1/”部分
```

* 正则表达式非命名组，通过位置参数传递给视图

```
url(r'^([0-9]+)/$', views.detail, name='detail'),
```

* 正则表达式命名组，通过关键字参数传递给视图，本例中关键字参数为id

```
url(r'^(?P<id>[0-9]+)/$', views.detail, name='detail'),
```

参数匹配的规则是优先使用命名参数，没有则使用位置参数。urlpatterns中每个正则表达式在第一次访问它们时被编译，所以使得系统相当快。

### 包含其他URLconfs

在应用中创建urls.py，里面定义要用的urlconf，而在settings中使用include\(\)将其包含进去。而在匹配过程中，会先与主URLconf匹配，成功后再用剩余的部分与应用中URLconf匹配。

这样使用include可以取出urlconf的冗余，而视图则会接收来自主URLconf和当前URLconf捕获的所有参数。而再include中通过namespace定义命名空间，用于反解析。

#### URL的反向解析

如果再视图和模板中使用硬编码的链接，则在urlconf发生改变时，维护成为非常麻烦的事情。

解决办法：在做链接时，通过指向urlconf的名称动态生成链接地址；视图中使用django.core.urlresolvers.reverse\(\)函数。应用模板中url标签。



