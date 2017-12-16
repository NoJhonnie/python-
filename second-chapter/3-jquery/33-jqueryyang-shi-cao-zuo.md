## jQuery样式操作

#### jQuery用法思想二

同一个函数完成取值和赋值

#### 操作行间样式

```
//获取div样式
$("div").css("width");
$("div").css("color");

//设置div样式
$("div").css("width","30px");
$("div").css({fontSize:"30px",color:"red"});
```

获取的多个元素，一般获取的是第一个，即$\("div"\).css\("width"\)获取第一个div的属性。

#### 操作样式类名

```
$("#div1").addClass("divClass2") //为id为div1的对象追加类名为divClass2的样式
$("#div1").removeClass("divClass")  //移除id为div1的对象的class名为divClass的样式
$("#div1").removeClass("divClass divClass2") //移除多个样式
$("#div1").toggleClass("anotherClass") //重复切换anotherClass样式
```



