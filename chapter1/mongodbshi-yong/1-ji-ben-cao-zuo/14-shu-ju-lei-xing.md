### MongoDB常用的数据类型

* ObjectID：文档ID
* String：字符串，必须是有效的UTF-8
* Boolean：存储布尔值，true或false
* Integer：整数32位或64位，取决于服务器
* Double：存储浮点值
* Arrays：数组或列表，多个值存储到一个键
* Object：用于嵌入式文档，一个值对应一个文档
* Null：存储Null值
* Timestamp：时间戳
* Date：存储当前日期或时间的UNIX时间格式

### object id

1. 每个文档都有一个属性，为\_id，保证每个文档的唯一性
2. 自己设置\_id出入文档
3. MongoDB为默认的每个文档提供独特的\_id，类型为objectID
4. objectID为一个12字节的十六进制数

* 前4个字节为时间戳
* 接着3个为机器ID
* 后来2个为MongoDB的服务经常id
* 最后3个为简单的增量值



