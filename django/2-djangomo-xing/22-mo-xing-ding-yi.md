## 模型定义

1.在模型中定义属性，会生成表中的字段

2.Django根据属性的类型确定以下信息：

* 当前数据库支持字段的类型
* 渲染管理表单时使用的默认html控件
* 管理站点最低限度的验证

3.Django会为表增加主键，但当设置某个属性为主键后，则Django不会再生成默认的主键列

4.属性命名限制

* 不能时python的保留关键字
* 不能使用连续的下划线，这个被本身的查询方式占用

### 定义属性

1.定义属性需要字段类型

2.字段类型先被定义再django.db.models.fields目录下，为了方便使用，被导入django.db.models中

3.使用方式：

* 导入from django.db import models
* 通过models.Field创建字段类型的对象，给属性赋值

4.对于重要数据做逻辑删除替代物理删除，设置isDelete类型为BooleanField，默认为False

### 字段类型

* AutoField：一个根据实际ID自动增长的IntegerField，通常不指定

* * 如果不指定，一个主键字段将自动添加到模型中
* BooleanField：true/false 字段，此字段的默认表单控制是CheckboxInput
* NullBooleanField：支持null、true、false三种值
* CharField\(max\_length=字符长度\)：字符串，默认的表单样式是 TextInput
* TextField：大文本字段，一般超过4000使用，默认的表单控件是Textarea
* IntegerField：整数
* DecimalField\(max\_digits=None, decimal\_places=None\)：使用python的Decimal实例表示的十进制浮点数
  * DecimalField.max\_digits：位数总数
  * DecimalField.decimal\_places：小数点后的数字位数
* FloatField：用Python的float实例来表示的浮点数
* DateField\[auto\_now=False, auto\_now\_add=False\]\)：使用Python的datetime.date实例表示的日期
  * 参数DateField.auto\_now：每次保存对象时，自动设置该字段为当前时间，用于"最后一次修改"的时间戳，它总是使用当前日期，默认为false
  * 参数DateField.auto\_now\_add：当对象第一次被创建时自动设置当前时间，用于创建的时间戳，它总是使用当前日期，默认为false
  * 该字段默认对应的表单控件是一个TextInput. 在管理员站点添加了一个JavaScript写的日历控件，和一个“Today"的快捷按钮，包含了一个额外的invalid\_date错误消息键
  * auto\_now\_add, auto\_now, and default 这些设置是相互排斥的，他们之间的任何组合将会发生错误的结果
* TimeField：使用Python的datetime.time实例表示的时间，参数同DateField
* DateTimeField：使用Python的datetime.datetime实例表示的日期和时间，参数同DateField
* FileField：一个上传文件的字段
* ImageField：继承了FileField的所有属性和方法，但对上传的对象进行校验，确保它是个有效的image

### 字段选项

通过字段选项，可以实现对字段的约束

* 在字段对象时通过关键字参数指定
* null：如果为True，Django 将空值以NULL 存储到数据库中，默认值是 False
* blank：如果为True，则该字段允许为空白，默认值是 False
* 对比：null是数据库范畴的概念，blank是表单验证证范畴的
* db\_column：字段的名称，如果未指定，则使用属性的名称
* db\_index：若值为 True, 则在表中会为此字段创建索引
* default：默认值
* primary\_key：若为 True, 则该字段会成为模型的主键字段
* unique：如果为 True, 这个字段在表中必须有唯一值

### 关系

总共三种关系：

* ForeignKey：一对多，将字段定义在多的一端
* ManyToManyField：多对多，两端都定义字段
* OneToOneField：一对一，任意一端

使用self可以维护递归的关联关系

```
用一访问多：对象.模型类小写_set
bookinfo.heroinfo_set
```

```
用一访问一：对象.模型类小写
heroinfo.bookinfo
```

```
访问id：对象.属性_id
heroinfo.book_id
```



