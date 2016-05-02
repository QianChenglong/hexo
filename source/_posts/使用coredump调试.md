---
title: 使用coredump调试
tags: [coredump, gdb]
date: 2015-08-15 12:03:47
---

1.  打开coredump生成功能

        ulimit -c unlimited

1.  查看core文件位置

        cat /proc/sys/kernel/core_pattern

1.  使用gdb调试

        gdb -c core文件 程序
