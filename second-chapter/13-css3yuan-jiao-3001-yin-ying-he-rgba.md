### CSS3圆角

设置某一个角的圆角，比如设置左上角的圆角：

```
border-top-left-radius:30px 60px;
```

同时分别设置四个角：

```
border-radius:30px 60px 120px 150px;
```

设置四个圆角相同：

```
border-radius:50%;
```

### CSS3阴影

分别设置阴影：水平偏移 垂直偏移 羽化大小 扩展大小 颜色 是否内阴影

```
box-shadow：h-shadow v-shadow blur spread color inset;
```

```
<style type="text/css">
    .box{
        width:200px;
        height:50px;
        background-color:gold;
        /* box-shadow:10px 10px 5px 2px pink inset; */
        box-shadow:10px 10px 5px 2px pink;
    }
</style>
......
<div class="box"></div>

<!-- 给盒子加上了粉红色的阴影 -->
```

### rgba（新的颜色值表示法） {#rgba（新的颜色值表示法）}

1、盒子透明度表示法：opacity:0.1;filter:alpha\(opacity=10\)（兼容IE）;  
2、rgba\(0,0,0,0.1\) 前三个数值表示颜色，第四个数值表示颜色的透明度

