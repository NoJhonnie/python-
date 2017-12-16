## jQuery属性操作

1.html\(\)取出或设置html内容

```
//取出内容
var $htm = $('#div1').html();

//设置html内容
$('#div1').html('<span>添加内容</span>');
```

2.text\(\)取出或设置text内容

```
//取出文本内容
var $htm = $('#div1').text();

//设置文本内容
$('#div1').text('<span>添加内容</span>');
```

3.attr\(\)取出或设置某个属性的值

```
//取出图片的地址
var $src = $('#img1').attr('src');

//设置图片的地址和alt属性
$('#img1').attr({src:"test.jpg", alt:"Test Image"});
```



