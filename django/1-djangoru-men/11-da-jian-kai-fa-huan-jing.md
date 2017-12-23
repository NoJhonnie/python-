## 创建项目

创建项目test1

```
django-admin startproject test1
```

test1目录下有文件夹test1和文件manage.py

#### 文件说明

manage.py：是一个命令行工具，用于多种方式对Django进行交互

内层的目录：项目的python包，包括四个文件

* \_\__init\_\_.py:里面没有内容，它主要是告诉python这个目录可以看成一个python包_
* setting.py：项目的配置
* urls.py：项目的URL声明
* wsgi.py：项目与WSGI兼容的web服务器入口



