---
title: select
tags: [linux, IO, select]
date: 2016-04-18 10:46:36
---

# 要点

## fd_set实现(`/usr/include/sys/select.h`)

-   描述符采用整数数组实现，通过bitmap来存储对应描述符

-   `FD_SETSIZE`默认为1024

        /usr/include/bits/typesizes.h
        #define __FD_SETSIZE        1024
