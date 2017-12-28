## 模板

Django作为Web框架提供了可以便利动态生成HTML的模板，它致力于表达外观，而非程序逻辑。而且模板的设计实现了业务逻辑与内容的分离，实现一个视图使用任意模板，而一个模板可以供多个视图使用。

该模板包括以下两部分：

* HTML静态部分和动态插入内容部分。

Django模板语言定义在django.template包中，由startproject命令生成的settings.py定义关于模板的值：

* DIRS定义了一个目录列表，模板引擎则按列表顺序搜索这些目录来查找模板源文件
* APP\_DIRS告诉模板引擎是否应该在每个已安装的应用中查找模板。

一般在项目的根目录下创建templates目录，设置DIRS值。

```
DIRS=[os.path.join(BASE_DIR,"templates")]
```

### 模板处理

Django处理模板分为两个阶段：

1.根据给定的标识找到模板然后预处理，通常会将它编译好放在内存中

```
loader.get_template(template_name),返回一个Template对象
```

2.使用Context数据对模板插值并返回生成的字符串

```
Template对象的render(RequestContext)方法，使用context渲染模板
```

加载渲染完整代码：

```
from django.template import loader,RequestContext
from django.http import HttpResponse

def index(request):
    tem = loader.get_template('temtest/index.html')
    context = RequestContext(request, {})
    return HttpResponse(tem.render(context))
```



