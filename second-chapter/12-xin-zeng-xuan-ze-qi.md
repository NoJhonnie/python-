## 新增选择器

1. E:nth-child\(n\)：匹配元素类型为E且是父元素的第n个子元素

```
<style type="text/css">            
    .list div:nth-child(2){
        background-color:red;
    }
</style>
......
<div class="list">
    <h2>1</h2>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
</div>

<!-- 第2个子元素div匹配 -->
```

1. E:nth-last-child\(n\)：匹配元素类型为E且是父元素的倒数第n个子元素（与上一项顺序相反）

2. E:first-child：匹配元素类型为E且是父元素的第一个子元素

3. E:last-child：匹配元素类型为E且是父元素的最后一个子元素

4. E:only-child：匹配元素类型为E且是父元素中唯一的子元素

5. E:nth-of-type\(n\)：匹配父元素的第n个类型为E的子元素

6. E:nth-last-of-type\(n\)：匹配父元素的倒数第n个类型为E的子元素（与上一项顺序相反）

7. E:first-of-type：匹配父元素的第一个类型为E的子元素

8. E:last-of-type：匹配父元素的最后一个类型为E的子元素

9. E:only-of-type：匹配父元素中唯一子元素是E的子元素

10. E:empty 选择一个空的元素

11. E:enabled 可用的表单控件

12. E:disabled 失效的表单控件

13. E:checked 选中的checkbox

14. E:not\(s\) 不包含某元素

15. E:target对应的锚点的样式

16. E&gt;F E元素下面的第一层子集

17. E~F元素后面的兄弟元素

18. E+F紧挨着的兄弟元素



