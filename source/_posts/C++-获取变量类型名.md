---
title: C++-获取变量类型名
categories: [C++]
tags: [C++]
date: 2015-07-01 13:51:18
---

```C++
int a = 1;
std::cout << typeid(a).name() << ":" << a << std::endl;
```

`./a.out | c++filt  -t`

# 参考

1.  <http://stackoverflow.com/questions/4465872/why-does-typeid-name-return-weird-characters-using-gcc-and-how-to-make-it-prin>
