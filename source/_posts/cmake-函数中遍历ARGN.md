---
title: cmake-函数中遍历ARGN
categories: [cmake]
tags: [cmake, 函数, 遍历, ARGN]
date: 2015-01-20 16:03:35
---

```cmake
function(use_library)
    foreach(name ${ARGN})
        if(${name} STREQUAL ".")
            include_directories(${PROJECT_SOURCE_DIR}/include)
            link_directories(${PROJECT_SOURCE_DIR}/lib)
        else()
            message(${PROJECT_SOURCE_DIR}/3rdparty/${name}/include)
            include_directories(${PROJECT_SOURCE_DIR}/3rdparty/${name}/include)
            link_directories(${PROJECT_SOURCE_DIR}/3rdparty/${name}/lib)
        endif()
    endforeach()
endfunction()
```

# 参考

1.  <http://www.cmake.org/cmake/help/v3.0/command/foreach.html>
