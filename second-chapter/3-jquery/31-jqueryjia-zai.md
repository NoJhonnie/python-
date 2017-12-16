## jQuery加载

以前我们都是将获取元素的语句写在页面头部，这会因为元素没有加载而出现错误，jQuery提供了ready方法来解决这个问题，而且速度比window.onload的更快。

```
<script type="text/javasript">
$(document).ready(function(){
    ...
});
</script>
```

简写

```
<script type="text/javasript">
$(function(){
    ...
});
</script>
```



