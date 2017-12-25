## 自连接

在同一张表格里可以自己连接自己，叫做自连接。地区信息就属于典型的自连接，本身地区信息属于一对多关系，但我们通过自连接将所有信息存储在一张表中。

新建模型AreaInfo，并进行迁移

```
class AreaInfo(models.Model):
    atitle = models.CharField(max_length=20)
    aParent = models.ForeignKey('self', null=True, blank=True)
注：该模型为自关联
```



