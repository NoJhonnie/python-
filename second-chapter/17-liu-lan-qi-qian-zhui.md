### 浏览器样式前缀

为了让CSS3样式兼容，需要将某些样式加上浏览器前缀：

-ms- 兼容IE浏览器  
-moz- 兼容firefox  
-o- 兼容opera  
-webkit- 兼容chrome 和 safari

```
div
{    
    -ms-transform: rotate(30deg);        
    -webkit-transform: rotate(30deg);    
    -o-transform: rotate(30deg);        
    -moz-transform: rotate(30deg);    
    transform: rotate(30deg);
}
```



