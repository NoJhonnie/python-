## less、sass、stylus

这是三种类似的动态语言，属于css预处理语言，他有类似css的语法，为css赋予动态特性，如变量、继承、运算、函数等，为了css的编写和维护。

less、sass编译软件：[http://koala-app.com/index-zh.html](http://koala-app.com/index-zh.html)

less中文网址：[http://lesscss.cn/](http://lesscss.cn/)

#### less语法

1.注释

```
//不会被编译的注释
/*注释有效*/
```

2.变量

```
@w:200px;
.box{
    width:@w;
    height:@w;
    background-color:red;
}
```

3.混合

```
.border{
    border:1px solid %dd;
}
.box(@w:100px, @h:50px,@bw:1px){
    width:@w;
    height:@h;
    border:@bw solid #ddd;
}
.box{
    .border;
    background-color:red;
}
```

4.匹配模式

```
.p(r){
    postion:relative;
}
.p(a){
    position:absolute;
}

.p(f){
    position:fixed;
}

.box{
    .p(f);
}
```

5.可以进行运算

```
@w:300px;
.box{
    width:@w+20;
}
```

6.嵌套

```
.list{
    li{
        ...
    }
    a{
        ...
        &:hover{
            ...
        }
    }
    span{
        ...
    }
}
```

7.导入

```
@import "common";    //导入common
@import (less) "a.css";    //导入a.css文件
```



