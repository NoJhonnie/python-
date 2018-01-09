##上传图片
django在处理文件时，文件数据被保存在request.FILES，FILES中的每个键为中的name。要注意FILES只有在请求的方法为POST且提交的<form>带有enctype=“multipart/form-data”的情况下才会包含数据，否则FILES将会传递一个空的类似字典的对象。
在使用模型处理上传文件时，将属性定义成models.ImageField类型
```
pic = models.ImageField(upload_to='cars/')
需要安装Pilow
pip install pillow==3.4.1
```
