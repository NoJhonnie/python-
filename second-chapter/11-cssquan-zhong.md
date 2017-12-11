## CSS权重

权重就是指样式的优先级，权重高的样式对元素起作用，相同时后写的样式覆盖前面的样式。

### 权重等级

一般将样式的应用方式分为以下几个等级：

1.!import，加在样式属性值后面，权重等级为10000

2.内联样式，例：style=“”，权重为1000

3.ID选择器，例：\#content，权重100

4.类，伪类和属性选择器，例：content、:hover权重10

5.标签选择器和伪类选择器，例：div、p、:before权重1

6.通用选择器\(\*\)、子选择器\(&gt;\)、相邻选择器\(+\)、同胞选择器\(~\)、权重值为0

```
<style type="text/css">
    #content div.main_content h2{
        color:red;    
    }
    #content .main_content h2{
        color:blue;
    }
</style>
......
<div id="content">
    <div class="main_content">
        <h2>这是一个h2标题</h2>
    </div>
</div>
<!-- 
第一条样式的权重计算： 100+1+10+1，结果为112；
第二条样式的权重计算： 100+10+1，结果为111；
h2标题的最终颜色为red
-->
```



