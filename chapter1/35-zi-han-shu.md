Mysql数据的内置函数

#### 字符串函数

* 查看字符的ascii码，字符串为空时返回0

```
select ascii('a');
```

* 查看ascii对应的字符char\(数字\)

```
select char(97);
```

* 拼接字符串

```
select concat(str1,str2...);
```

* 包含字符个数

```
select length('ab');
```

* 截取字符串

1. left\(str,len\)返回字符串str的左端len个字符；
2. right\(str,len\)返回字符串str的右端len个字符；
3. substring\(str,pos,len\)返回字符串str的位置pos起len个字符。

```
select substring('abc123',2,3);
```

* 去除空格

1. ltrim\(str\)返回删除了左空格的字符串str；
2. rtrim\(str\)返回删除了右空格的字符串str；
3. trim\(方向 restr from str\)返回从某测删除restr后的字符串str，方向词包括both、leading、trailing对应两侧、左、右。

```
select trim('  str   ');
select trim(leading 'x' from 'xxxstrxxx');
select trim(trailing 'x' from 'xxxstrxxx');
select trim(both 'x' from 'xxxstrxxx');
```

* 返回由n个空字符组成的字符串

```
select space(7);
```

* 替换字符串replace\(str,from\__str,to\__str\)

```
select replace('abc123','123','def');
```

* 大小写转换

1. lower\(str\)
2. upper\(str\)

```
select lower('AbdcDe');
```

#### 数字函数

* 求绝对值

```
select abs(-34);
```

* 求余数，同运算符%

```
select mod(10,3);
select 10%3;
```

* 地板，表示不大于数字的最大整数

```
select floor(2.5);
```

* 天花板，表示不小于数字的整数

```
select ceiling(2.4);
```

* 四舍五入

```
select round(n,d); n表示原数，d表示小数位
```

* x的y次幂

```
select pow(x,y); x的y次幂
```

* 圆周率

```
select PI();
```

* 随机数，值为0-1.0的

```
select rand();
```

#### 日期时间函数

* 获取子值的语法

1. year\(date\)年份范围1000-9999
2. month\(date\)月份
3. day\(date\)日期
4. hour\(time\)小时数0-23
5. minute\(time\)分钟数0-59
6. second\(time\)秒数0-59

```
select year('2016-12-21');
```

日期计算使用+-运算符，后面接year、month、day、hour、minute、second

```
select '2017-11-23'+interval 1 day;
```



