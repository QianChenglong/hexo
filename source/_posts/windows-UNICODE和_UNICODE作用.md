---
title: windows-UNICODE和_UNICODE作用
categories: [windows]
tags: [windows, UNICODE, _UNICODE]
date: 2015-03-02 14:12:14
---

# 共性

这两个宏都是为了控制API是使用UNICODE版还是ANSI版。

-   若定义了，则相关的API为`*W`版本(UNICODE版)，如`GetWindowTextW`

-   若未定义，则相关的API为`*A`版本(ANSI版)，如`GetWindowTextA`

# 区别

-   `UNICODE`宏影响windows API

-   `_UNICODE`宏影响C运行库以及MFC，作用与`UNICODE`

# 参考

1.  <http://blogs.msdn.com/b/oldnewthing/archive/2004/02/12/71851.aspx>
1.  <http://www.cnblogs.com/ini_always/archive/2011/05/20/2050517.html>
