---
title: windows-_T和__T
categories: [windows]
tags: [windows, macro, _T, __T]
date: 2015-03-02 15:48:25
---

# 定义

`tchar.h`

```c
#define __T(x)      L ## x
#define _T(x)       __T(x)
```

# 疑问

-   为什么不直接定义`#define _T(x) L ## x`呢？

    因为在处理类似`_T(__FILE__)`时，会被拓展成`L__FILE__`，而`L__FILE__`则是未定义标识符

    -   为什么这样能做到？

        `_T(__FILE__)`先拓展`__FILE__`，在插入到该表达式，然后进行**合并**操作

# 参考

1.  <http://cpp.ezbty.org/myfiles/boost/libs/wave/doc/macro_expansion_process.html>
1.  <https://gcc.gnu.org/onlinedocs/cppinternals/Macro-Expansion.html>
1.  <https://msdn.microsoft.com/zh-cn/library/09dwwt6y.aspx>
1.  <https://gcc.gnu.org/onlinedocs/cpp/Concatenation.html>
