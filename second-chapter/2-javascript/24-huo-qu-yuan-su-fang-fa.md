## 获取元素方法

使用内置对象document的getElementById方法获取页面id属性，获取到的是一个html对象，然后赋值变量。

```
<script type="text/javascript">
    var oDiv = document.getElementById('div1');
</script>
....
<div id="div1">这是一个div元素</div>
```

这样写在元素的上面会出现一个问题，因为页面是从上往下加载执行，js去页面上获取div1的时候，元素div1还没加载，解决方法：

1.将js放到页面最下边

```
....
<div id="div1">这是一个div元素</div>
....

<script type="text/javascript">
    var oDiv = document.getElementById('div1');
</script>
</body>
```

2.将js放在window.onload触发的函数里面，获取元素的语句会在页面加载完后才执行。

```
<script type="text/javascript">
    window.onload = function(){
        var oDiv = document.getElementById('div1');
    }
</script>

....

<div id="div1">这是一个div元素</div>
```



