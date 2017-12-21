## less、sass、stylus

这是三种类似的动态语言，属于css预处理语言，他有类似css的语法，为css赋予动态特性，如变量、继承、运算、函数等，为了css的编写和维护。

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



