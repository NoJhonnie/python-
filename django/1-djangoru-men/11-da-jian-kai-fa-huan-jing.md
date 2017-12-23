## 创建项目

创建项目test1

```
django-admin startproject test1
```

test1目录下有文件夹test1和文件manage.py

#### 文件说明

manage.py：是一个命令行工具，用于多种方式对Django进行交互

内层的目录：项目的python包，包括四个文件

* \_\__init\_\_.py:里面没有内容，它主要是告诉python这个目录可以看成一个python包\_
* setting.py：项目的配置
* urls.py：项目的URL声明
* wsgi.py：项目与WSGI兼容的web服务器入口

#### 虚拟环境

有时候不同项目需要不同的类库，而同一个系统的类库只有一个，为了避免将所有类库都安装到系统环境中导致的不同项目类库问题，使得不同项目的类库遗存不再成为问题，我们需要virtualenv虚拟环境。

注：最好以下安装使用管理员权限的cmd，不然可能出现权限受限而出现安装失败

安装virtualenv

```
pip install virtualenv
```

新建虚拟环境

```
virtualenv test1
注：虚拟环境位于当前目录下，例如你cmd当前目录为C:\Users\Gogh>，
则在Gogh下创建虚拟环境
```

进入虚拟环境

```
1.进入上面创建虚拟环境的test1目录中；
2.进入目录的Scripts目录；
3.运行activate.bat
```

查看虚拟环境中默认的安装库

```
pip list
```

退出

```
在Scripts目录中，运行deactivate.bat
```

#### virtualenvwrapper

每次进入虚拟环境，我们都要进入相应的目录，环境创建过多，则导致效率低下，因此需要virtualenvwrapper。

安装virtualenvwrapper

```
pip install virtualenvwrapper-win
注：linux下运行pip install virtualenvwrapper
```

设置WORKON\_HOME系统环境变量

```
默认创建虚拟环境的位置位于电脑用户下的envs中，不利于管理，因此设置环境变量
```

相应的操作

```
创建：mkvirtualenv [虚拟环境名称]
删除：rmvirtualenv [虚拟环境名称]
进入：workon [虚拟环境名称]
退出：deactivate
查看当前所有虚拟环境：workon [两次tab]
查看已经安装的包：pip list;pip freeze
```



