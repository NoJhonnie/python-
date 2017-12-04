一、编辑interfaces 

```
sudo vi  /etc/network/interface
```

二、编辑该文件

```
auto lo
iface lo inet loopback
auto ens33
iface ens33 inet static
address 192.168.8.100
netmask 255.255.255.0
gateway 192.168.8.2
dns-nameserver 8.8.8.8
```

注：其中ens33 和 lo是自己的网卡名字，可以用语句查询

```
ifconfig -a
```

三、重启网络

```
sudo /etc/init.d/networking restart
```

至此vmvare上的虚拟机ip地址就变成静态IP地址了。

