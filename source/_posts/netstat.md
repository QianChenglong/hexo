---
title: netstat
tags: [netstat]
date: 2015-08-05 13:49:59
---

-   -t  查看tcp

-   -x  查看unix域套接字

-   -l  只查看listen端口

-   -n  端口数字显示，不解释其所代表服务，以便加快速度

-   -p  查看所属进程

# etc

Recv-Q：表示收到的数据已经在本地接收缓冲，但是还有多少没有被进程取走
Send-Q：对方没有收到的数据或者说没有Ack的，还在发送缓冲区

# 常用命令

-   查看tcp监听端口

        netstat -tln
