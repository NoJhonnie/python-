## 数组

JavaScript的数组数据可以是不同类型。

#### 定义数组的方法

```
var aList = new Array(1,2,3);    //实例创建
var aList2 = [1,2,3,'abc'];    //直接创建
```

#### 操作数组中数据方法

1.获取数组长度：aList.length;

2.操作某个数组的数据：aList\[0\];

3.将数组成员通过一个分隔符合并成字符串：aList.join\('@'\)

```
var aList = [1,2,3,4];
alert(aList.join('@')); // 弹出 1@2@3@4
```



