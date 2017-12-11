## 操作元素属性

对页面元素的属性进行操作，属性的操作包括属性的读写。

#### 操作属性的方法：

1."."操作

2."\[\]"操作

```
<!-- “.”操作属性 -->
<script type="text/javascript">

    window.onload = function(){
        var oInput = document.getElementById('input1');
        var oA = document.getElementById('link1');
        // 读取属性值
        var val = oInput.value;
        var typ = oInput.type;
        var nam = oInput.name;
        var links = oA.href;
        // 写(设置)属性
        oA.style.color = 'red';
        oA.style.fontSize = val;
    }

</script>

......

<input type="text" name="setsize" id="input1" value="20px">
<a href="http://www.baidu.com" id="link1">百度</a>
```

```
<!-- “[]”操作属性  -->
<script type="text/javascript">

    window.onload = function(){
        var oInput1 = document.getElementById('input1');
        var oInput2 = document.getElementById('input2');
        var oA = document.getElementById('link1');
        // 读取属性
        var val1 = oInput1.value;
        var val2 = oInput2.value;
        // 写(设置)属性
        // oA.style.val1 = val2; 没反应
        oA.style[val1] = val2;        
    }

</script>

......

<input type="text" name="setattr" id="input1" value="fontSize">
<input type="text" name="setnum" id="input2" value="30px">
<a href="http://www.baidu.com" id="link1">百度</a>
```

#### 属性的写法

1.html的写法和js属性写法一样

2."class"属性写出"className"

3."style"属性里面的属性，有横杆的改写成驼峰式，例”font-Size“，改写成style.fontSize

#### innerHTML

innerHTML读取或写入标签包裹内容

```
<script type="text/javascript">
    window.onload = function(){
        var oDiv = document.getElementById('div1');
        //读取
        var txt = oDiv.innerHTML;
        alert(txt);
        //写入
        oDiv.innerHTML = '<a href="http://www.baidu.com">百度竞价<a/>';
    }
</script>

......

<div id="div1">这是一个div元素</div>
```



