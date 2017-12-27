## HTTP Response对象

在django.http模块中定义了HttpResponse对象的API，HttpRequest对象由Django自动创建，而HttpResponse对象由自己创建，该对象不用调用模板直接返回数据。

### 属性

* content：返回的内容，字符串类型
* charset：response采用的编码字符集，字符串类型
* status\_code：响应的HTTP响应状态码
* content-type：指定输出的MIME类型



