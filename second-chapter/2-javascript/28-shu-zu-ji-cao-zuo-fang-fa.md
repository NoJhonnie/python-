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

4.从数组最后增加成员或删除成员：aList.push\(\)和pop\(\)

5.从数组前面增加成员或删除成员：aList.unshift\(\)和shift\(\)

6.数组反转：aList.reverse\(\)

7.返回数组中元素第一次出现的索引值：aList.indexOf\(\)

8.在数组中增加或删除成员

```
var aList = [1,2,3,4];
aList.splice(2,1,7,8,9); //从第2个元素开始，删除1个元素，然后在此位置增加'7,8,9'三个元素
alert(aList); //弹出 1,2,7,8,9,4
```



