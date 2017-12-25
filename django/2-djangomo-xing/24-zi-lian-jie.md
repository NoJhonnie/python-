## 自连接

在同一张表格里可以自己连接自己，叫做自连接。地区信息就属于典型的自连接，本身地区信息属于一对多关系，但我们通过自连接将所有信息存储在一张表中。

* 新建模型AreaInfo，并进行迁移

```
class AreaInfo(models.Model):
    atitle = models.CharField(max_length=20)
    aParent = models.ForeignKey('self', null=True, blank=True)
注：该模型为自关联
```

* 加入数据，在booktest/views.py中定义视图area

```
from models import AreaInfo
def area(request):
    area = AreaInfo.objects.get(pk=130100)
    return render(request, 'booktest/area.html', {'area': area})
```

定义模板area.html

```
<!DOCTYPE html>
<html>
<head>
    <title>地区</title>
</head>
<body>
当前地区：{{area.atitle}}
<hr/>
上级地区：{{area.aParent.atitle}}
<hr/>
下级地区：
<ul>
    { %for a in area.areainfo_set.all%}
    <li>{{a.atitle}}</li>
    { %endfor%}
</ul>
</body>
</html>
```

* 在booktest/urls.py配置新的urlconf

```
urlpatterns = [
    url(r'^area/$', views.area, name='area')
]
```



