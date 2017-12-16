## jQuery选择器

#### jQuery的用法思想

就是选取某个网页元素，然后对他进行操作

#### jQuery选择器

jQuery选择器可以快速选择元素，规则与css样式相同，使用length属性判断是否选择成功。

```
$(document)    //选择整个文档对象
$('li')    //选择所有li元素
$('#myId')    //选择id为myId的网页元素
$('.myClass')    //选择class为myClass的元素
$('input[name=first]')    //选择name属性为first的input元素
$('#ul1 li span')    //选择id为ul1元素下的所有li下的span元素
```

#### 对选择集进行修饰过滤\(类似CSS伪类\)

```
$('#ul1 li:first')    //选择id为ul1元素下的第一个li
$('#ul1 li:odd')    //选择id为ul1元素下li的奇数行
$('#ul1 li:eq(2)')    //选择id为ul1元素下li的第3行
$('#ul1 li:gt(2)')    //选择id为ul1元素下li的前3个之后的li
$('#myForm:input')    //选择表单中的input元素
$('div:visible')    //选择可见的div元素
```



