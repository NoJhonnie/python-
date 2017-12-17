## 滚轮事件及函数节流

#### **jquery.mousewheel插件使用**

jquery中没有鼠标滚轮事件，原生js中的鼠标滚轮事件不兼容，可以使用jquery的滚轮事件插件jquery.mousewheel.js。

#### **函数节流**

javascript中有些事件的触发频率非常高，比如onresize事件\(jq中是resize\)，onmousemove事件\(jq中是mousemove\)以及上面说的鼠标滚轮事件，在短事件内多处触发执行绑定的函数，可以巧妙地使用定时器来减少触发的次数，实现函数节流。



