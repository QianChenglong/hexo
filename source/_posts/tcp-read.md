---
title: tcp-read
tags: [tcp, read]
date: 2016-03-11 19:26:53
---

    ssize_t read(int fildes, void *buf, size_t nbyte);

# 返回值

-   >0，成功读取了n字节

-   =0，对方断开了连接

-   <0，发生了错误

    -   EINTR   被中断，没有读取到数据
