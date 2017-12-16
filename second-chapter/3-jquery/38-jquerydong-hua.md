## jQuery动画

通过animate方法可以设置元素某属性值上的动画，可以设置一个或多个属性值，动画执行完之后会执行一个函数。

```
$('#div1').animate({
    width:300,
    height:300
},1000,swing,function(){
    alert('done!');
});

//参数：
1.属性设置{pra1:1，pra1:2}
2.speed 时间 ms
3.swing 默认值 开始和结束缓慢，中间快速；liner 匀速
4.回掉函数
```

参数也可以写成数字表达式

```

```



