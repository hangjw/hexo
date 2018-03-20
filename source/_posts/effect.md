---
layout: "\x96open_basedir"
title: open_basedir restriction in effect 的问题
date: 2017-03-15 13:22:28
tags: centos 
---

出现open_basedir restriction in effect 的问题的解决方法
============

### 步骤一、 [修改fastcgi的配置文件 /usr/local/nginx/conf/fastcgi.conf   ]

        fastcgi_param PHP_ADMIN_VALUE "open_basedir=$document_root/:/tmp/:/proc/:/var/winwww/";

### 步骤二、 [修改php.ini的配置文件 /usr/local/php/etc/php.ini   ]

        open_basedir=/data/wwwroot/test.org/:/tmp/

