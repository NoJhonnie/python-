### 主动触发

可以使用jQuery对象上的trigger方法来触发对象上绑定的事件

### 自定义事件

通过band方法自定义事件，用tiggle方法触发事件

```
//给element绑定hello事件
element.bind("hello",function(){
    alert("hello！");
});

//触发hello事件
element.trigger("hello");
```



