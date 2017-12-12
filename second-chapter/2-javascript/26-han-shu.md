## 函数

重复执行的代码。

函数的定义和执行

```
<script type="text/javascript">
    function an(){
        alert('hello world!')
    }

    an();
</script>
```

### 变量与函数预解析

Javascript解析分为两个阶段，先是编译阶段，然后执行阶段，编译阶段会见将function定义的函数提前，并将var定义的变量声明提前，将它赋值为undefined。

```
<script type="text/javascript">    
    aa();       // 弹出 hello！
    alert(bb);  // 弹出 undefined
    function aa(){
        alert('hello!');
    }
    var bb = 123;
</script>
```

#### 提取行间事件

html行间调用的事件可以提取到JavaScript中调用，从而做到结构与行分离。

```
<!--行间事件调用函数   -->
<script type="text/javascript">        
    function myalert(){
        alert('ok!');
    }
</script>
......
<input type="button" name="" value="弹出" onclick="myalert()">

<!-- 提取行间事件 -->
<script type="text/javascript">

window.onload = function(){
    var oBtn = document.getElementById('btn1');
    oBtn.onclick = myalert;
    function myalert(){
        alert('ok!');
    }
}    
</script>
......
<input type="button" name="" value="弹出" id="btn1">
```

#### 匿名函数

定义函数可以不给名称称之为匿名函数，将匿名函数直接赋值给元素绑定的事件完成函数的调用。

```
<script type="text/javascript">

window.onload = function(){
    var oBtn = document.getElementById('btn1');
    /*
    oBtn.onclick = myalert;
    function myalert(){
        alert('ok!');
    }
    */
    // 直接将匿名函数赋值给绑定的事件

    oBtn.onclick = function (){
        alert('ok!');
    }
}

</script>
```

#### 函数传参

```
<script type="text/javascript">
    function myalert(a){
        alert(a);
    }
    myalert(12345);
</script>
```

#### 函数‘return’关键字

作用：

1.返回函数执行的结果

2.结束函数的运行

3.阻止默认行为

```
<script type="text/javascript">
function add(a,b){
    var c = a + b;
    return c;
    alert('here!');
}

var d = add(3,4);
alert(d);  //弹出7
</script>
```



