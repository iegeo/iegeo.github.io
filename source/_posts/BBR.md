---
title: BBR
date: 2018-03-18 02:02:12
tags: BBR
categories: 资料
---
Linux内核4.9以上支持TCP BBR，可以到[这里](http://kernel.ubuntu.com/~kernel-ppa/mainline/)下载:

### 下载安装包:
 ```shell
 wget http://kernel.ubuntu.com/~kernel-ppa/mainline/*...*.deb
 ```
<!--more-->
### 安装:
```
dpkg -i linux-image*.deb
```
### 查看卸载旧内核: 
```s
dpkg -l | grep linux-image
apt-get purge *...*
```

### 更新引并重启:
```
update-grub
reboot
```

开启bbr
```bash
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
sysctl net.ipv4.tcp_available_congestion_control
lsmod | grep bbr
```