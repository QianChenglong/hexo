---
title: 使用宏控制dll导入或导出
categories: [C]
tags: [C, dll, macro]
date: 2015-03-26 11:09:56
---

```c
#pragma once

#ifdef XXX_HAS_DLL
#   ifdef XXX_BUILD_DLL
#       if defined(_MSC_VER) || defined(__BORLANDC__) || defined(__MINGW32__)
#           define LOG4CPP_EXPORT __declspec(dllexport)
#               else
#           define LOG4CPP_EXPORT
#               endif
#   else
#       if defined(_MSC_VER) || defined(__BORLANDC__) || defined(__MINGW32__)
#           define LOG4CPP_EXPORT __declspec(dllimport)
#               else
#           define LOG4CPP_EXPORT
#               endif
#   endif
#else
#   define XXX_EXPORT
#endif
```

**说明：**

-   XXX为库名称

-   XXX_HAS_DLL 编译器是否支持`__declspec(dllexport)`

-   XXX_BUILD_DLL 动态库内部使用，还是供外部引用

-   XXX_EXPORT 用来说明某个变量，函数，类是否为导出或导入


# 参考

1.  log4cpp/include/Export.hh
1.  <https://gcc.gnu.org/wiki/Visibilit>
