---
title: python-from import VS import
categories: [python]
tags: [python, from import, import]
date: 2015-03-31 15:34:30
---

# from A.B.C import D

-   C之前的名字必须是包名

-   C必须是模块名

    不能是已定义的名字(变量，函数，类)，如果这样的话，D没有意义

-   D名字导入进来，可以直接使用`D.name`访问

# import A.B

-   最后部分可以是包名，模块名，已定义名字

-   需要使用`A.B.name`访问

# 参考

1.  <https://docs.python.org/2/tutorial/modules.html#packages>
