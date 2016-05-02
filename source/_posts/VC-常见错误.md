---
title: VC-常见错误
categories: [VC]
tags: [VC, 错误]
date: 2015-03-11 14:24:45
---

# `lily.lib(WinSock.cpp.obj) : error LNK2038: 检测到“_ITERATOR_DEBUG_LEVEL”的不匹配项: 值“0”不匹配值“2”(dhcpcd.obj 中)`

-   原因：

    `debug`版程序链接了`release`版库

    -   在`cmake`中，`TAGET_LINK_LIBRARIES`中，没有单独链接相应版本的库。

-   解决：

    重新设置对应的库名称

    -   cmake

        LIST(APPEND LIBS debug lilyd optimized lily)
        TARGET_LINK_LIBRARIES(${PROJECT_NAME} ${LIBS})
