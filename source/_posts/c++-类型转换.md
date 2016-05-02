---
title: c++-类型转换
tags: [c++]
date: 2016-02-27 19:31:51
---

# `static_cast`

-   相关类型的转换，如整型到枚举，浮点到整型

# `reinterpret_cast`

-   互不相关类型转换，如整型到指针

# `const_cast`

-   去除`const`，`volatile`修饰

# `dynamic_cast`

-   多态类型的转换

    1.  子类向基类的向上转型(Up Cast)
    2.  基类向子类的向下转型(Down Cast)
    3.  横向转型(Cross Cast)
