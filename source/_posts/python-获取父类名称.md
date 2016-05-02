---
title: python-获取父类名称
categories: [python]
tags: [python, 父类]
date: 2015-04-03 11:24:09
---

# 通过`__bases__`属性

    str.__bases__

# 通过`inspect`模块

    inspect.getmro(str)

__注：__

-   mro:method resolution order

# 参考

1.  <http://stackoverflow.com/questions/2611892/get-python-class-parents>
