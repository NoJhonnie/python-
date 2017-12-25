## 模型查询

在管理器上调用过滤器方法会返回查询集，查询集经过过滤器筛选后返回新的查询集。一般会有**惰性执行**，即创建查询集不会带来任何数据库的访问，直到调用数据时，才会访问数据库。而返回查询集的方法则称之为过滤器。

* all\(\)
* filter\(\)
* exclude\(\)
* order\_by\(\)
* values\(\) 将一个对象构造成一个字典，然后构成一个列表返回。

```
filter(键1=值1，键2=值2)
```

以上查询都是返回集合，也可以返回单个值的方法：

* get\(\)返回单个满足条件的对象
  * 如果未找到，则发生DoesNoExist的异常
  * 多条返回，则引发MultipleObjectsReturned异常
* count\(\)返回当前查询的总数
* first\(\)返回第一个对象
* last\(\)返回最后一个对象
* exists\(\)判断查询集合中是否有数据，有则返回True

#### 限制查询集

在返回的列表中，可以使用下标的方式进行限制，等同于sql中的limit和offset，但注意不支持负数索引。而且使用下标后返回一个新的查询集，不会立即执行查询。如果获取一个对象，直接使用\[0\]，则等同于\[0:1\].get\(\)，但若没有数据，则会引发IndexError异常，\[0:1\].get\(\)引发DoesNotExist异常。

#### 查询集缓存

每个查询集都包含一个缓存来最小化对数据库的访问，在新建的查询集中，缓存为空。当首次查询集求值时，会发生数据库查询，Django会在将查询的结果存在查询集的缓存中，并返回请求的结果。而接下来对查询集求值，则会重用缓存的结果。可以分为以下两种情况：

情况一：构成两个查询集，无法重用缓存，每次查询都会与数据库进行交互，增加数据库的负载。

```
print([e.title for e in Entry.objects.all()])
print([e.title for e in Entry.objects.all()])
```

情况二：两次循环使用同一个查询集，第二次使用缓存中的数据。

```
querylist=Entry.objects.all()
print([e.title for e in querylist])
print([e.title for e in querylist])
```

当只对查询集的部分进行求值时，会检查缓存，但如果这部分不在缓存中，那么接下来查询返回的记录将不会被缓存。换句话说使用索引来限制查询集将不会填充缓存，如果这部分数据已经被缓存，则直接使用缓存中的数据。

### 字段查询

为了实现sql中where的功能，将其作为方法filter\(\)、exclude\(\)、get\(\)的参数。通用语法：属性名称\_\_比较运算符=值，其中两个下划线的左侧是属性名称，右侧是比较类型。使用“属性名\_id ”表示外键的原始值。

```
filter(title__contains="%")=>where title like '%\%%'
表示查找标题中包含%的
```

#### 比较运算符

* exact：表示判等，大小写敏感；如果没有写“

```
filter(isDelete=False)
```

* contains：是否包含，大小写敏感

```
exclude(btitle__contains='传')
```

* startswith、endswith：以value开头或结尾，大小写敏感

```
exclude(btitle__endswith='传')
```

* isnull、isnotnull：是否为null

```
filter(btitle__isnull=False)
```

* 在前面加个i表示不区分大小写，如iexact、icontains、istarswith、iendswith
* in：是否包含在范围内

```
filter(pk__in=[1, 2, 3, 4, 5])
```

* gt、gte、lt、lte：大于、大于等于、小于、小于等于

```
filter(id__gt=3)
```

* year、month、day、week\_day、hour、minute、second：对日期间类型的属性进行运算

```
filter(bpub_date__year=1980)
filter(bpub_date__gt=date(1980, 12, 31))
```

* 跨关联关系的查询：处理join查询
  * 语法：模型类名&lt;属性名&gt;&lt;比较&gt;
  * 注：可以没有\_\_&lt;比较&gt;部分，表示等于，结果同inner join
  * 可返向使用，即在关联的两个模型中都可以使用

```
filter(heroinfo__hcontent__contains='八')
```

* 查询的快捷方式：pk，pk表示primary key，默认的主键是id

```
filter(pk__lt=6)
```

### 聚合函数

