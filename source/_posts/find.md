---
title: find
categories: [linux]
tags: [linux, command, find]
date: 2015-06-18 10:04:01
---

# 功能

查找文件，非常强大！

# 常用选项

-   -mtime

    -   n 在n天之前**一天内**的文件
    -   +n 在n天之前,**不包含从现在到n天**这段时间
    -   -n n天内

    ![](../img/find_01.png)

# 实例

-   查找/下最近1天修改过文件

        find / -mtime 0
