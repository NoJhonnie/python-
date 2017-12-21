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

## 前端自动化

#### Node.js {#nodejs}

Node.js可以理解为是一门后端脚本语言，使用了和JavaScript相同的语法，会使用JavaScript的程序员能很快上手node.js、nodjs在处理高并发方面性能卓越，目前许多公司都在使用nodejs作为后端数据服务和前端开发的中间层。

node.js的中文网站：[https://nodejs.org/zh-cn/](https://nodejs.org/zh-cn/)

#### 前端自动化 {#前端自动化}

前端开发的流程越来越复杂，其中有代码的合并和压缩、图片的压缩；对less、sass的预处理；文件操作等，这些工作是重复乏味的，为了优化开发流程，提高工作效率，前端自动化工具就出现了，自动化工具可以通过配置，自动完成这些工作。

#### grunt、gulp {#grunt、gulp}

grunt和gulp是使用node.js编写的，前端首选的自动化工具，gulp在书写配置上比grunt更简洁，运行的性能更高，gulp逐渐成为主流。

#### gulp的使用 {#gulp的使用}

gulp使用步骤： 安装nodejs -&gt; 全局安装gulp -&gt; 项目安装gulp以及gulp插件 -&gt; 配置gulpfile.js -&gt; 运行任务 gulp网站：[http://gulpjs.com/](http://gulpjs.com/)

常用gulp插件：  
压缩js代码（gulp-uglify）  
less的编译（gulp-less）  
css的压缩 （gulp-minify-css）  
自动添加css3前缀（gulp-autoprefixer）  
文件改名字 \(gulp-rename\)

## 前端性能优化

通过技术手段和优化策略，缩短访问和呈现速度。

一.代码部署

1.代码压缩和合并

2.图片、js、css等静态资源使用和主站不同域名地址存储，从而使得在传输时不会带上不必要cookie信息。

3.使用内容分发网络CDN

4.为文件设置Last-Modified、Expires和Etag

5.使用GZIP压缩传送

6.权衡DNS查找次数

7.避免不必要的重定向加（“/”）

## 二.编码

#### html： {#html：}

1、使用结构清晰，简单，语义化标签  
2、避免空的src和href  
3、不要在HTML中缩放图片

#### css： {#css：}

1、精简css选择器 2、把CSS放到顶部  
3、避免@import方式引入样式  
4、css中使用base64图片数据取代图片文件，减少请求数，在线转base64网站：[http://tool.css-js.com/base64.html](http://tool.css-js.com/base64.html)  
5、使用css动画来取代javascript动画  
6、使用字体图标,图标库网站：[http://fontawesome.io/icons/，在线制作网站：www.iconfont.cn](http://fontawesome.io/icons/，在线制作网站：www.iconfont.cn)  
7、使用css sprite  
8、使用svg图形  
9、避免使用CSS表达式

10、避免使用滤镜

#### javascript： {#javascript：}

1、减少引用库的个数  
2、使用requirejs或seajs异步加载js  
3、JS放到页面底部引入  
4、避免全局查找  
5、减少属性查找  
6、使用原生方法  
7、用switch语句代替复杂的if else语句  
8、减少语句数，比如说多个变量声明可以写成一句  
9、使用字面量表达式来初始化数组或者对象  
10、使用DocumentFragments或innerHTML取代复杂的元素注入  
11、使用事件代理\(事件委托\)  
12、避免多次访问dom选择集  
13、高频触发事件设置使用函数节流，如：onmousemove、onmouseover  
14、使用Web Storage缓存数据  
15、使用Array的join方法来代替字符串的“+”连接\(先将要连接的字符串放进数组\)

