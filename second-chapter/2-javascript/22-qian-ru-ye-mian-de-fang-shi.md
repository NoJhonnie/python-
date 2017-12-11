## 嵌入页面的方式

1.行间事件

```
<input type="button" name="" onclick="alert('ok!');">
```

2.页面script标签嵌入

```
<script type="text/javascript">
    var a = 'hello!';
    alert(a);
</script>
```

3.外部引入

```
<script type="text/javascript" src="js/index.js"></script>
```

## 语句与注释

1.语句以“;“结尾

```
<script type="text/javascript">    
var a = 123;
var b = 'str';
function fn(){
    alert(a);
};
fn();
</script>
```

2.注释

```
<script type="text/javascript">    

// 单行注释
var a = 123;
/*  
    多行注释
    1、...
    2、...
*/
var b = 'str';
</script>
```



