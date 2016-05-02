---
title: extern "C"
categories: [C]
tags: [C, extern]
date: 2015-03-26 11:34:25
---

# 作用

当使用C++编译器对C++源码编译时，对C函数采用"C"语言方式编译和连接(函数导出名不变)

# 为什么需要`extern "C"`

因为C++支持函数重载，所以对函数名存在修饰操作。

若一个函数为普通全局函数，制作为dll，其他C程序进行调用，当编译该程序采用C编译器，无法找到该符号，因为C编译器与C++编译器对函数名的修饰规则不一致！

所以为了使C编译器能够使用这些函数，需要使用`extern "C"`声明。

# 惯用法

```c++
#ifdef __cplusplus
extern "C" {
#endif

...

#ifdef __cplusplus
}
# endif
```
