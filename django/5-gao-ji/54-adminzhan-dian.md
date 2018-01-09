##Admin站点
我们通过startproject创建的项目模板中，默认Admin是被启用的。我们通过创建管理员的用户名和密码，再在应用中admin.py文件完成注册，就可以在后台管理中维护模型的数据。
##ModelAdmin对象
我们有时候想要自己定义一个Admin模型，而ModelAdmin就是模型在Admin的界面中的表现形式。
* 通常在admin.py的文件中定义一个类，注册模型时使用这个类，该类继承admin.ModelAdmin；
* 使用该类有两个方法：1、注册参数；2、注册装饰器。
```
注册参数
admin.site.register(HeroInfo,HeroAdmin)
注册装饰器
@admin.register(HeroInfo)
class HeroAdmin(admin.ModelAdmin)
```
* 通过重写admin.ModelAdmin的属性规定显示效果，而属性主要分为列表页和增加修改页两部分。
##InlineModelAdmin对象
该对象是表示模型的添加或修改页面嵌入关联模型的添加或修改。其中TabularInline：是以表格的形式嵌入的；StackedInline：以块的形式嵌入。
##重写admin模板
有时候我们想要一个好看一点的admin目录，我们可以在项目所在目录中创建templates目录，再建一个admin目录。设置模板查找目录，即修改settings.py的TEMPLATES项，加载模板时会在DIRS列表指定的目录中搜索
```
'DIRS':[os.path.join(BASE_DIR, 'templates')],
```
然后从django安装的目录下（django/contrib/admin/templates）键模板页面的源文件admin/base_site.html拷贝到创建好的目录里。接着对源文件进行编辑就ok了。