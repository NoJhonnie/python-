### 集合创建

```
db.createCollection(name, options)
```

* name是要创建的集合名称
* options是一个文档，用于指定集合的配置，可选

例1：不填写默认，不限制大小

```
db.createCollection("students")
```

例2：限制大小

```
db.createCollection("teachers",{capped:true,size:10})
```

* capped：true设置上限
* size：表示上限大小，单位为字节

### 查看集合

```
show collections
```

### 删除

```
db.集合名称.drop()
```



