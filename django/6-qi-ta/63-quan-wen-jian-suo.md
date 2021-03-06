# 全文检索 {#全文检索}

* 全文检索不同于特定字段的模糊查询，使用全文检索的效率更高，并且能够对于中文进行分词处理
* haystack：django的一个包，可以方便地对model里面的内容进行索引、搜索，设计为支持whoosh,solr,Xapian,Elasticsearc四种全文检索引擎后端，属于一种全文检索的框架
* whoosh：纯Python编写的全文搜索引擎，虽然性能比不上sphinx、xapian、Elasticsearc等，但是无二进制包，程序不会莫名其妙的崩溃，对于小型的站点，whoosh已经足够使用
* jieba：一款免费的中文分词包，如果觉得不好用可以使用一些收费产品

# 操作 {#操作}

#### 1.在虚拟环境中依次安装包 {#1在虚拟环境中依次安装包}

```
pip install django-haystack
pip install whoosh
pip install jieba

```

#### 2.修改settings.py文件 {#2修改settingspy文件}

* 添加应用

```
INSTALLED_APPS = (
    ...
    'haystack',
)

```

* 添加搜索引擎

```
HAYSTACK_CONNECTIONS = {
    'default': {
        'ENGINE': 'haystack.backends.whoosh_cn_backend.WhooshEngine',
        'PATH': os.path.join(BASE_DIR, 'whoosh_index'),
    }
}

#自动生成索引
HAYSTACK_SIGNAL_PROCESSOR = 'haystack.signals.RealtimeSignalProcessor'

```

#### 3.在项目的urls.py中添加url {#3在项目的urlspy中添加url}

```

urlpatterns = [
    ...
    url(r'^search/', include('haystack.urls')),
]

```

#### 4.在应用目录下建立search\_indexes.py文件 {#4在应用目录下建立searchindexespy文件}

```
# coding=utf-8
from haystack import indexes
from models import GoodsInfo


class GoodsInfoIndex(indexes.SearchIndex, indexes.Indexable):
    text = indexes.CharField(document=True, use_template=True)

    def get_model(self):
        return GoodsInfo

    def index_queryset(self, using=None):
        return self.get_model().objects.all()

```

#### 5.在目录“templates/search/indexes/应用名称/”下创建“模型类名称\_text.txt”文件 {#5在目录templatessearchindexes应用名称下创建模型类名称texttxt文件}

```
#goodsinfo_text.txt，这里列出了要对哪些列的内容进行检索
{{ object.gName }}
{{ object.gSubName }}
{{ object.gDes }}

```

#### 6.在目录“templates/search/”下建立search.html {#6在目录templatessearch下建立searchhtml}

```
<!DOCTYPE html>
<html>
<head>
    <title></title>
</head>
<body>
{% if query %}
    <h3>搜索结果如下：</h3>
    {% for result in page.object_list %}
        <a href="/{{ result.object.id }}/">{{ result.object.gName }}</a><br/>
    {% empty %}
        <p>啥也没找到</p>
    {% endfor %}

    {% if page.has_previous or page.has_next %}
        <div>
            {% if page.has_previous %}<a href="?q={{ query }}&amp;page={{ page.previous_page_number }}">{% endif %}&laquo; 上一页{% if page.has_previous %}</a>{% endif %}
        |
            {% if page.has_next %}<a href="?q={{ query }}&amp;page={{ page.next_page_number }}">{% endif %}下一页 &raquo;{% if page.has_next %}</a>{% endif %}
        </div>
    {% endif %}
{% endif %}
</body>
</html>
```

#### 7.建立ChineseAnalyzer.py文件 {#7建立chineseanalyzerpy文件}

* 保存在haystack的安装文件夹下，路径如“/home/python/.virtualenvs/django\_py2/lib/python2.7/site-packages/haystack/backends”

```
import jieba
from whoosh.analysis import Tokenizer, Token


class ChineseTokenizer(Tokenizer):
    def __call__(self, value, positions=False, chars=False,
                 keeporiginal=False, removestops=True,
                 start_pos=0, start_char=0, mode='', **kwargs):
        t = Token(positions, chars, removestops=removestops, mode=mode,
                  **kwargs)
        seglist = jieba.cut(value, cut_all=True)
        for w in seglist:
            t.original = t.text = w
            t.boost = 1.0
            if positions:
                t.pos = start_pos + value.find(w)
            if chars:
                t.startchar = start_char + value.find(w)
                t.endchar = start_char + value.find(w) + len(w)
            yield t


def ChineseAnalyzer():
    return ChineseTokenizer()

```

#### 8.复制whoosh\_backend.py文件，改名为whoosh\_cn\_backend.py {#8复制whooshbackendpy文件，改名为whooshcnbackendpy}

* 注意：复制出来的文件名，末尾会有一个空格，记得要删除这个空格

```
from .ChineseAnalyzer import ChineseAnalyzer 
查找
analyzer=StemmingAnalyzer()
改为
analyzer=ChineseAnalyzer()

```

#### 9.生成索引 {#9生成索引}

* 初始化索引数据

```
python manage.py rebuild_index

```

#### 10.在模板中创建搜索栏 {#10在模板中创建搜索栏}

```
<form method='get' action="/search/" target="_blank">
    <input type="text" name="q">
    <input type="submit" value="查询">
</form>
```



  


