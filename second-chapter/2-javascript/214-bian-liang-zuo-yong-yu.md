## 变量作用域

变量的作用范围，JavaScript的作用域分为全局变量和布局变量

1.全局变量：定义在函数之外的变量，作用于整个页面，函数内外都可以使用；

2.局部变量：定义在函数内的变量，只能用于函数内。

```
<script type="text/javascript">
    //全局变量
    var a = 12;
    function myalert()
    {
        //局部变量
        var b = 23;
        alert(a);
        alert(b);
    }
    myalert(); //弹出12和23
    alert(a);  //弹出12    
    alert(b);  //出错
</script>
```



