---
title: virtualbox安装Ubuntu server16，配置双网卡
date: 2018-03-20 03:41:39
categories: 资料
tags:
---
目的：实现在virtualBox安装多个虚拟机，虚拟机版本选择最新Ubuntu server16，每个虚拟机设置两个网卡一个NAT，一个hostonly。

NAT：实现虚拟机访问外部网络
hostonly：实现虚拟机之间的相互访问<!--more-->
1. 点击虚拟机设置-网络，网卡1，选择：网络地址转换NAT；网卡2，选择hostonly
2. 打开虚拟机，此时只有网卡1生效，网卡2并未配置网络地址；查看网络配置ifconfig
显示只有网络enp0s3,，即网卡1NAT模式下的网络分配。输入ifconfig -a，查看所有网卡
看到网卡2：enp0s8，但是未分配IP地址，表明这个网卡没有使用。enp0s3是新的Linux系统新的命名规则，原来的是eth0的形式。
此时网卡1是可用的，输入ping www.baidu.com 是可以ping通的。但是此时网卡2不可用，虚拟机之间无法ping通。如果设置网卡1为hostonly而网卡2位NAT，则虚拟机之间可以通，但是ping www.baidu.com 不通。

3. 使第二个网卡生效
进入etc/network目录，打卡interfaces，查看原来的配置
此处确实只有enp0s3这个网卡的配置，加入enp0s8网卡的配置，sudo vi interfaces  ，在后面增加enp0s8网络的配置