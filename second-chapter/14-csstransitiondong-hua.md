## transition动画

1、transition-property 设置过渡的属性，比如：width height background-color  
2、transition-duration 设置过渡的时间，比如：1s 500ms  
3、transition-timing-function 设置过渡的运动方式

* linear 匀速
* ease 开始和结束慢速
* ease-in 开始是慢速
* ease-out 结束时慢速
* ease-in-out 开始和结束时慢速
* cubic-bezier\(n,n,n,n\)
  * 比如：cubic-bezier\(0.845, -0.375, 0.215, 1.335\)
  * 曲线设置网站：
    [https://matthewlein.com/ceaser/](https://matthewlein.com/ceaser/)

4、transition-delay 设置动画的延迟  
5、transition: property duration timing-function delay 同时设置四个属性

```
<style type="text/css">        
.box{
    width:100px;
    height:100px;
    background-color:gold;
    transition:width 300ms ease,height 300ms ease 300ms,background-color 300ms ease 600ms;            
}
.box:hover{
    width:300px;
    height:300px;
    background-color:red;
}
</style>
......
<div class="box"></div>

<!-- hover时，依transition的顺序依次显示动画 -->
```



