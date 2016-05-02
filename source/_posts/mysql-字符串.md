---
title: mysql-字符串
tags: [mysql, char, varchar]
date: 2015-07-16 14:21:05
---

# 存储

-   `char(N)`, `varchar(N)`,N指的是**特定字符集下的**字符长度

    -   latin1下,char(1)占1字节
    -   utf-8下,char(1)占1~4字节,汉字一般占3字节

# 长度判断

-   `length()` 获取字符串占用多少字节

-   `char_length()` 获取字符串长度(特定字符集下的字符个数)
