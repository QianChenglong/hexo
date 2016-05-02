---
title: C++-静态数据成员
tags: [c++, static]
date: 2016-04-28 15:20:56
---

```c++
class X
{
public:
  int normalValue = 5;
  static const int i = 0;       // declaration, with initializer
};

const int X::i;                 // definition
```

# 要点

-   与全局变量存储在同一区域(全局/静态存储区，又叫做数据段)

-   在函数内用static修饰的变量，也是在**全局/静态存储**，只是访问的**作用域**被编译器限定

-   static数据成员只是加上了类名字限定了的全局变量！

# 为什么需要在类实现文件中单独定义static类型数据成员？

-   因为类定义在头文件中，而头文件可以在不同的object中引用，
    这样该定义不唯一，链接器在链接时，会报重定义错误！


# 参考

1.  <http://stackoverflow.com/questions/11300652/static-data-member-initialization>
1.  <http://programmers.stackexchange.com/questions/145299/why-the-static-data-members-have-to-be-defined-outside-the-class-separately-in-c>
1.  <http://en.cppreference.com/w/cpp/language/static>
