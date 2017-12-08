### $unwind

将文档中的某一个数组字段拆分成多条，每条包含数组中的一个值

```
db.集合.aggregate([{$unwind:'$字段名称'}])
```

* 构造数据

```
db.t2.insert({_id:1,item:'t-shirt',size:['S','M','L']})
```

* 查询

```
db.t2.aggregate([{$unwind:'$size'}])
```

```
db.t3.aggregate([{$unwind:'$sizes'}])
```

* 对某字段值进行拆分

```
db,inventory.aggregate([{
    $unwind:{
    path:'$字段名称',
    preserveNullAndEmptyArrays:<boolean>    #防止数据丢失
    }
}])
```

```
db.t3.aggregate([{$unwind:{path:'$size',preserveNullAndEmptyArrays:true}}])
```

* 构造数据

```
db.t3.insert([
{"_id":1,"item":"a","size":["S","M","L"]},
{"_id":2,"item":"b","size":[]},
{"_id":3,"item":'c',"size":"M"},
{"_id":4,"item":"d"},
{"_id":5,"item":"e","size":null}
])
```



