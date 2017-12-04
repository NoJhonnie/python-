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

* left\(str,len\)返回字符串str的左端len个字符；

* right\(str,len\)返回字符串str的右端len个字符；
* substring\(str,pos,len\)返回字符串str的位置pos起len个字符。

```
select substring('abc123',2,3);
```

* 去除空格

* ltrim\(str\)返回删除了左空格的字符串str；

* rtrim\(str\)返回删除了右空格的字符串str；
* trim\(方向 restr from str\)返回从某测删除restr后的字符串str，方向词包括both、leading、trailing对应两侧、左、右。

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

* 替换字符串replace\(str,from\_\_str,to\_\_str\)

```
select replace('abc123','123','def');
```

* 大小写转换

* lower\(str\)

* upper\(str\)

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

* year\(date\)年份范围1000-9999

* month\(date\)月份
* day\(date\)日期
* hour\(time\)小时数0-23
* minute\(time\)分钟数0-59
* second\(time\)秒数0-59

```
select year('2016-12-21');
```

* 日期计算使用+-运算符，后面接year、month、day、hour、minute、second

```
select '2017-11-23'+interval 1 day;
```

* 日期格式化date\_formate\(date,format\),formate参数如下：

1. 获取年%Y，返回4位的整数
2. 获取年%y，返回2位的整数

3. 获取月%m，值为1-12的整数

4. 获取日%d，返回整数

5. 获取时%H，值为0-23的整数

6. 获取时%h，值为1-12的整数

7. 获取分%i，值为0-59的整数

8. 获取秒%s，值为0-59的整数

```
select date_formate('2017-12-05','%Y %m %d');
```

* 当前日期

```
select current_date();
```

* 当前时间

```
select current_time();
```

* 当前日期时间

```
select now();
```



