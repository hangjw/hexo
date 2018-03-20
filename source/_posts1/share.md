---
title: windows和虚拟机共享目录
date: 2017-03-12 12:45:45
tags: centos
---

说明：
windows下有一共享文件夹APP，windows本地ip是192.168.9.155
现在需要在linux服务器上挂载这个APP文件夹，linux服务器ip是192.168.9.200
操作记录如下：

### 1）windows上的准备工作
    首先将windows上D盘下的APP文件夹设置为共享。右击APP文件夹的“共享”属性.
{% asset_img 1.jpg This is an example image %}
{% asset_img 2.jpg This is an example image %}
{% asset_img 3.jpg This is an example image %}
{% asset_img 4.jpg This is an example image %}
### 2）linux服务器上的操作
    创建挂载目录/mnt/APP
    mount -t cifs -o username=WindowsLogin,password="passwordinWindows" //16.187.190.50/test /mnt/
### 3）检查
    df -h

##卸载

### 1） 卸载
    umount /mnt/APP
### 2） 检查 
    umount /mnt/APP