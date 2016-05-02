---
title: valgrind-使用
categories: [valgrind]
tags: [valgrind]
date: 2015-02-11 14:29:20
---

# 说明

-   编译时需要加入调试信息，这样才能定位哪里溢出

# 检测

    valgrind --tool=memcheck --leak-check=yes --show-reachable=yes --num-callers=20 --track-fds=yes ./test
