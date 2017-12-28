## 定义模板

模板语言包括：变量、标签{% 代码块 %}、过滤器和注释{ \# 代码或html \#}

### 变量

```
{{variable}}
```

当一个模板引擎遇到一个变量时，将计算这个变量，然后输出结果。变量名必须由字母、数字、下划线和点组成。当模板引擎遇到点\("."\)时，会安装下列顺序查询：

* 字典查询，如foo\["bar"\]
* 属性或方法查询，如foo.bar
* 数字索引查询，如foo[bar]

如果变量不存在，模板将插入''（空字符串），这就导致调用方法不能传递参数。
###在模板中调用对象的方法
1.在models.py定义类HeroInfo
2.在views.py中传递HeroInfo对象
3.最后在detail.html中调用
###标签
标签的语法：\{% tag %}，作用
* 在输出中创建文本
* 控制循环或逻辑
* 加载外部信息到模板中，供以后的变量使用
####for标签
```
{% for ...in... %}
循环的逻辑
{{forloop.counter}}表示当前的循环次数
{% empty %}
给出的列表或列表不存在时，执行
{% endfor %}
```
####if标签

```
{%if ...%}
逻辑1
{%elif ...%}
逻辑2
{% else %}
逻辑3
{% endif %}
```
####comment标签
```
{% comment %}
多行注释
{% endcomment %}
```
####include
加载模板并以标签内的参数渲染
```
{%include "foo/bar.html"%}
```
####url
反向解析
```
{% url 'name' p1 p2 %}
```
####csrf_token
这个标签用于跨站请求伪造保护
```
{% csrf_token %}
```
* 布尔标签：and、or、and比or的优先级高
* block、extends：用于模板继承
* autoescape：HTML转义
###过滤器