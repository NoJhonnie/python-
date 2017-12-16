## jQuery选择器

#### jQuery的用法思想一

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

#### 对选择集进行函数过滤

```
$('div').has('p'); // 选择包含p元素的div元素
$('div').not('.myClass'); //选择class不等于myClass的div元素
$('div').filter('.myClass'); //选择class等于myClass的div元素
$('div').first(); //选择第1个div元素
$('div').eq(5); //选择第6个div元素
```

#### 选择集转移

```
$('div').prev(); //选择div元素前面的第一个p元素
$('div').prevAll(); //选择div同级元素前面的所有元素，可以在()中进行选择
$('div').next();    //选择div同级元素的下一个元素
$('div').nextAll(); //选择div同级元素后面的所有元素，可以在()中进行选择
$('div').closest('form'); //选择离div最近的那个form父元素，多层选择用这个
$('div').parent(); //选择div的父元素
$('div').children(); //选择div的所有子元素
$('div').siblings(); //选择div的同级元素
$('div').find('.myClass'); //选择div内的class等于myClass的元素
```

```
$('.list li') //不能回到父级
$('.list').children()  //可以通过end()回到父级
```



