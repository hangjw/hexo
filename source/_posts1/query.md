---
layout: "\x96open_basedir"
title: http_build_query 的问题
date: 2017-05-15 13:22:18
tags: php 
---

发送请求方，http_build_query与接收方值不同的解决方法
============

在php客户端方，如果某个键的值为null是不会进入http_build_query函数调用之后的数据，
在服务端放，如果某个参数为空字符串则认为是null，而客户端方认为是空字符串会引起数据的不一致。