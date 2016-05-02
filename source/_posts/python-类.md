---
title: python-类
categories: [python]
tags: [python, 类]
date: 2015-04-02 10:35:54
---

# 特点

-   python中的类是C++和Modula-3的混合体

-   C++角度，所有成员使用`public`，所有方法都是`virtual`

-   和Modula-3一样，python没有隐式关联对象与数据和方法

    所有方法在定义时，显示声明第一个参数`self`

    在调用时，self隐式赋值

-   同stmalltalk一样，类本身也是对象，此机制提高了导入和重命名语义

-   同C++和Modula-3不一样的是，内置类型可以被拓展

-   允许多重继承

-   子类可以重写父类的任何方法

-   子类可以调用父类中的同名方法

-   子类`__init__`如果需要，必须显式调用父类`__init__`方法

-   类可以被动态创建，且可以在创建之后被修改
