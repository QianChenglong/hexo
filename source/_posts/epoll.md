---
title: epoll
tags: [epoll]
date: 2016-03-15 17:34:30
---

# 要点

-   `epoll_event`中的`epoll_data_t`用来存储用户自定义数据

    当与其绑定的`fd`上发生指定的事件时，`epoll_wait`返回该`event`，用户可以拿到该数据
