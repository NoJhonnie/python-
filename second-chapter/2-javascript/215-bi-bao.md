## 闭包

函数嵌套函数，内部函数可以引用外部函数的参数和变量，参数和变量不会被垃圾回收机制回收。

```
//一般函数
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
 
 //闭包函数
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



