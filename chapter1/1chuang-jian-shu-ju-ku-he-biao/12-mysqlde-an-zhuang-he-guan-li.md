## 安装

* ubuntu的系统

```
sudo apt-get install mysql-server mysql-client
```

* window系统

下载mysql客户端，mysql官网[https://www.mysql.com/](https://www.mysql.com/)

## 管理服务

* 启动

```
service mysql start
```

* 停止

```
service mysql stop
```

* 重启

```
service mysql restart
```

## 远程连接

* 找mysql配置文件修改

```
sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
注释bind-address=127.0.0.1
```

* 登陆mysql运行命令

```
grant all privileges on *.* to 'root'@'%' identified by 'mysql' with grant option;
flush privileges;
```

* 重启mysql



