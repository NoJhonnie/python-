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