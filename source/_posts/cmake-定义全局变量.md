---
title: cmake-定义全局变量
categories: [cmake]
tags: [cmake, 全局变量]
date: 2015-01-21 14:33:06
---

```cmake
set(UTEST_LIBRARIES ${ARGN} CACHE INTERNAL "UTEST_LIBRARIES")
```

# 参考

1.  <http://stackoverflow.com/questions/10031953/how-to-set-the-global-variable-in-a-function-for-cmake>
1.  <http://www.cmake.org/cmake/help/v3.0/command/set.html>
