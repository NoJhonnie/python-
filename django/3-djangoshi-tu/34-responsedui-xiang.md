## HTTP Response对象

在django.http模块中定义了HttpResponse对象的API，HttpRequest对象由Django自动创建，而HttpResponse对象由自己创建，该对象不用调用模板直接返回数据。

### 属性

* content：返回的内容，字符串类型
* charset：response采用的编码字符集，字符串类型
* status\_code：响应的HTTP响应状态码
* content-type：指定输出的MIME类型

### 方法

* init：使页面内容实例化HttpResponse对象
* write\(content\)：以文件方式写
* flush\(\)：以文件的方式输出缓存区
* set\_cookie\(key, value='', max\_age=None, xpires=None\)：设置Cookie

  * key、value都是字符串类型
  * max\_age是一个整数，表示在指定秒数后过期
  * expires是一个datetime或timedelta对象，会话将在这个指定的日期/时间过期，注意datetime和timedelta值只有在使用PickleSerializer时才可序列化
  * max\_age与expires二选一
  * 如果不指定过期时间，则两个星期后过期

delete\_cookie\(key\)：删除指定key的Cookie，如果没有则不发生。

