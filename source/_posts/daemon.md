---
title: daemon
tags: [linux, daemon]
date: 2016-04-26 11:27:58
---

# 步骤

1.  关闭打开的文件描述符(0,1,2等，可通过`ls /proc/pid/fd`查看打开的文件描述符)

    若不关闭，虽然没有了控制终端，不会接受到相应控制信号，则仍能IO对应文件，如标准输出到启动时的终端，从终端读入！

    -   需要注意，默认为行缓冲！
