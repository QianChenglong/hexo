---
title: cmake-打印Include路径列表
categories: [cmkae]
tags: [cmake, include]
date: 2015-01-29 15:45:03
---

```cmake
get_property(dirs DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY INCLUDE_DIRECTORIES)
foreach(dir ${dirs})
  message(STATUS "dir='${dir}'")
endforeach()
```

# 参考

1.  <http://stackoverflow.com/questions/6902149/listing-include-directories-in-cmake>
