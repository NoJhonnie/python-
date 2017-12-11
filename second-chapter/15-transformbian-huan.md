## CSS3 transform变换

1. translate\(x,y\) 设置盒子位移
2. scale\(x,y\) 设置盒子缩放
3. rotate\(deg\) 设置盒子旋转
4. skew\(x-angle,y-angle\) 设置盒子斜切
5. perspective 设置透视距离
6. transform-style flat \| preserve-3d 设置盒子是否按3d空间显示
7. translateX、translateY、translateZ 设置三维移动
8. rotateX、rotateY、rotateZ 设置三维旋转
9. scaleX、scaleY、scaleZ 设置三维缩放
10. tranform-origin 设置变形的中心点
11. backface-visibility 设置盒子背面是否可见

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>翻面</title>
    <style type="text/css">
        .box{
            width:300px;
            height:272px;
            margin:50px auto 0;
            transform-style:preserve-3d;    /* 变换风格为3d，默认为平面 */
            position:relative;            
        }
        .box .pic{
            width:300px;
            height:272px;
            position:absolute;
            background-color:cyan;
            left:0;
            top:0;
            transform:perspective(800px) rotateY(0deg);
            backface-visibility:hidden;
            transition:all 500ms ease;
        }
        .box .back_info{
            width:300px;
            height:272px;
            text-align:center;
            line-height:272px;
            background-color:gold;
            position:absolute;
            left:0;
            top:0;
            transform:rotateY(180deg);
            backface-visibility:hidden;
            transition:all 500ms ease;            
        }
        .box:hover .pic{
            transform:perspective(800px) rotateY(180deg);
        }
        .box:hover .back_info{
            transform:perspective(800px) rotateY(0deg);
        }
    </style>
</head>
<body>
    <div class="box">        
        <div class="pic"><img src="images/location_bg.jpg"></div>
        <div class="back_info">背面文字说明</div>
    </div>
</body>
</html>
```



