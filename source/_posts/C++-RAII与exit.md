---
title: C++-RAII与exit
categories: [C++]
tags: [C++, RAII, exit]
date: 2015-03-11 15:49:16
---

# `exit`执行析构函数情况

-   不会执行**栈**空间上的类变量的析构函数！所以，在使用`RAII`时，调用`exit`会使其失效。

-   全局变量会执行析构函数

-   `static`存储类型也会执行析构函数

# 参考

1.  <http://blog.copton.net/archives/2007/04/23/raii_vs__exit/index.html>
1.  <http://www.zhihu.com/question/20765487>
