##分页
django提供了一些类实现管理数据分页，类位于django/core/paginator.py中。
### Paginator对象
Paginator(list, int)：传递两个参数list和int，返回分页对象，参数list为列表数据，int为每面数据的条数。
它有以下三个**属性**：
* count:对象总数
* num_pages:页面总数
* page_range:页码列表，从1开始，[1,2,3,4]

它的方法：
* page(num):下标以1开始，如果不存在则抛出InvalidPage异常。

存在以下异常exception:
* InvalidPage:page()传入一个无效的页码时抛出；
* PageNotAnInteger：传入page()不是整数；
* EmptyPage:传入page()值没有对象时。

###Page对象
Paginator对象的page()方法返回Page对象，不需要手动构造。它有以下属性：
* object_list:当前页上所有对象的列表；
* number:当前页的序号，从1开始；
* paginator：当前page对象相关的Paginator对象。

该对象方法：
* has_next():如果有一页返回True；
* has_previous()：如果有上一页返回True；
* has_other_pages():有上页或下页返回True；
* next_page_number():返回下一页的页码，如果没有则抛出InvalidPage异常；
* previous_page_number():返回上一页的页码，如果没有则抛出InvalidPage异常；
* len():返回当前页面对象的个数；
迭代页面对象：访问当前页面中的每个对象。