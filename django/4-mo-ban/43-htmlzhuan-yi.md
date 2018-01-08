## HTML转义
django回对字符串进行自动HTML转义，即对包含的html标签进行输出，而不是解释执行。django会对以下字符进行自动转义：
```
<转换成&lt
