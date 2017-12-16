## jQuery事件

#### 事件函数列表：

```
blur()    失去焦点
focus()    获得焦点
change()    表单元素的值发生变化
click()    鼠标单击
dbclick()    鼠标双击
mouseover()    鼠标进入(子元素也包括)
mouseout()    鼠标离开(包括子元素)
mouseenter()    鼠标进入(不包括子元素)
mouseleave()    鼠标离开(不包括子元素)
hover()    同时为mouseenter和mouseleave事件指定处理函数
mouseup()    松开鼠标
mousedown()    按下鼠标
mousemove()    鼠标在元素内部移动
keydown()    按下键盘
keypress()    按下键盘
keyup()    松开键盘
load()    元素加载完毕
ready()    DOM加载完毕
resize()    浏览器窗口大小发生变化
scroll()    滚动条位置发生变化
select()    用户选中文本框内容
submit()    用户递交表单
toggle()    根据鼠标点击的次数，依次运行多个函数
unload()    用户离开页面
```

#### 绑定事件的方法

```
$(function(){
    $('div1').bind('mouseover click', fucntion(event){
        alert($(this).html());
        
        //取消绑定事件
        $(this).unbind();
        //指定取消事件
        $(this).unbind('mouseover')
    });
});
```

#### 取消绑定事件



