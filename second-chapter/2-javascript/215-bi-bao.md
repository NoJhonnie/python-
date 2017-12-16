## 闭包

函数嵌套函数即函数内部定义函数，内部函数可以引用外部函数的参数和变量，参数和变量不会被垃圾回收机制回收。这是因为一般将嵌套函数赋给一个变量，只要这个变量没有被回收，则该嵌套函数也不会被回收。

```
//一般的闭包函数
function aaa(a){      
      var b = 5;      
      function bbb(){
           a++;
           b++;
         alert(a);
         alert(b);
      }
      return bbb;
  }

 var ccc = aaa(2);

 ccc();
 ccc();

 //封闭函数的闭包
 var ccc = (function(a){

  var b = 5;
  function bbb(){
       a++;
       b++;
     alert(a);
     alert(b);
  }
  return bbb;

})(2);

ccc();
ccc();
```

用处：

1.将一个变量长期贮存在内存中，用于循环中索引值

2.私有化变量计数器，外部无法访问，避免全部变量的污染

