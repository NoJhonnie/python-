## 尺寸和滚动事件

1.获取和设置元素的尺寸

```
width()、height()    获取元素width和height  
innerWidth()、innerHeight()  包括padding的width和height  
outerWidth()、outerHeight()  包括padding和border的width和height  
outerWidth(true)、outerHeight(true)   包括padding和border以及margin的width和height
```

2.获取元素相对页面的绝对位置

```
offse()
```

3.获取可视区高度

```
$(window).height()
```

4.获取页面高度

```
$(document).height()
```

5.获取页面滚动距离

```
$(document).scrollTop()
$(document).scrollLeft()
```

6.页面滚动事件

```
$(window).scroll(function(){
    ...
})
```



