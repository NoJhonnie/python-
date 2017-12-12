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



