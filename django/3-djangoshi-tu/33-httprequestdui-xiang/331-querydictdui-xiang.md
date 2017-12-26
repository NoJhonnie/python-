### QueryDict对象

该对象定义在django.http.QueryDict中，request对象的GET和POST都是QueryDict类型的对象。QueryDict类型的对象是用来处理同一个键带有多个值的情况。

* get\(\)是根据键获取值，只能获取键的一个值，如果一个键拥有多个值，则获取最后一个值。
* getlist\(\)根据键获取值，它可以获取多个值。



