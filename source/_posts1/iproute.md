---
layout: 
title: centos配置ip
date: 2017-04-15 9:22:28
tags: centos 
---

centos配置ip
============
###1. 初次安装centos不可缺少的就是配上必要的ip。
{% asset_img 1.png This is an example image %}

###2. 接下来正常是用VI命令编辑网络配置文件了，命令：vi /etc/sysconfig/network-scripts/ifcfg-eht0。
{% asset_img 2.png This is an example image %}

###3. 写入配置内容。
    DEVICE=eth0
    TYPE=Etherne
    tUUID=58d64342-6bca-4156-8d4b-3bb092190644
    ONBOOT=yes
    NM_CONTROLLED=yes
    BOOTPROTO=none
    HWADDR=00:15:5D:01:44:11
    IPADDR=192.168.1.103
    PREFIX=24
    GATEWAY=192.168.1.251
    DNS1=202.96.128.86
    DNS2=8.8.8.8
    DEFROUTE=yes
    IPV4_FAILURE_FATAL=yes
    IPV6INIT=no
    NAME="System eth0"

解说如下：

1、网卡对应的设备别名，如ifcfg-eth0的文件中它为eth0

2、网络类型：以太网
UUID含义是通用唯一识别码 (Universally Unique Identifier)，在此可以忽略

3、ONBOOT=自动加载
NM_CONTROLLED在此可以忽略，如需联网，BOOTPROTO设为static(静态地址)即可，可选值dhcp(动态地址)

4、HWADDR=00:15:5D:01:44:11 网卡MAC地址（这个是我的，你别抄哦）

5、IPADDR=192.168.1.103 网络ip地址

6、PREFIX=24 子网掩码24位

7、GATEWAY=192.168.1.251  网关地址8、DNS1=10.203.104.41  主DNS地址

9、DNS1=10.203.104.41  备用DNS地址