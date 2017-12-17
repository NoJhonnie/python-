## 事件委托

就是利用事件冒泡原理，将事件加到共有的父级上，通过判断事件的子集来执行相应的操作，可以减少事件绑定次数，提高性能；同时也可以让新加入的子元素拥有相同的操作。

#### 事件委托写法

```
//一般写法
$(function(){
    $ali = $('#list li');
    $ali.click(function(event) {
        $(this).css({background:'red'});
    });
})

//事件委托方法
$(function(){
    $list = $('#list');
    $list.delegate('li', 'click', function(event) {
        $(this).css({background:'red'});
        
        //取消事件委托
        $list.undelegate();
    });
})
...
<ul id="list">
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
</ul>
```



