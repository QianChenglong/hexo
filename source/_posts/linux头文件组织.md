---
title: linux头文件组织
tags: [linux]
date: 2016-03-19 14:41:04
---

通过`yum provides FILENAME`来查找所属包

-   glibc-headers(使用C开发库，必须安装的包)

    `/usr/include/sys`，`/usr/include/bits`

-   kernel-headers(被glibc使用)

    `/usr/include/linux`，`/usr/include/asm`
