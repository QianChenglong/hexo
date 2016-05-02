---
title: mysql-mysql_use_result-VS-mysql_store_result
tags: [mysql, mysql_use_result, mysql_store_result]
date: 2015-08-17 16:53:41
---

# mysql_use_result

保留了如何从服务器取结果集

## 优势

-   客户端占用内存小

-   

## 劣势

-   不能随机访问结果行

-   必须访问完,才能获取行数

-   客户端对结果处理必须得快,否则对服务端造成压力

-   必须从服务端获取所有结果,即使已经找到需要的行

# mysql_store_result

将sql执行结果全部获取到客户端

## 优势

-   能直接获取结果行数

-   能随机访问结果行

## 劣势

-   客户端占用内存大,可能内存溢出

# 共同点

-   都需要调用`mysql_free_result`释放内存

# 参考

1.  mysql-manual.23.8.6
