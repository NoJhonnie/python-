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

## 封闭函数

封闭函数是JavaScript里匿名函数的另一种写法，创建一个一开始就执行而不命名的函数。

```
//一般函数
function changecolor(){
    var oDiv = document.getElementById('div1');
    oDiv.style.color = 'red';
}
changecolor();

//封闭函数
(function(){
    var oDiv = document.getElementById('div1');
    oDiv.style.color = 'red';
})();

//也可以在函数定义前加“~”或“！”来定义匿名函数
!function(){
    var oDiv = document.getElementById('div1');
    oDiv.style.color = 'red';
}()
```



