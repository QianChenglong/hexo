---
title: cmake-if
categories: [cmake]
tags: [cmake, if]
date: 2015-01-20 16:06:07
---

# 字符串比较

```cmake
if(${name} STREQUAL ".")
    include_directories(${PROJECT_SOURCE_DIR}/include)
    link_directories(${PROJECT_SOURCE_DIR}/lib)
    return()
endif()
```

# 参考

1.  <http://www.cmake.org/cmake/help/v3.0/command/if.html>
