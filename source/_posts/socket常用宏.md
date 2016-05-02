---
title: socket常用宏
categories: [socket]
tags: [socket, 宏]
date: 2015-02-27 10:53:11
---

| 宏名            | 值         | winsock2               | linux                     |
|-----------------+------------+------------------------+---------------------------|
| AF_INET         | 2          | winsock2.h => ws2def.h | socket.h => bits/socket.h |
| INADDR_LOOPBACK | 0x7f000001 | winsock2.h => ws2def.h | netinet/in.h              |
| SOCKET_ERROR    | -1         | winsock2.h             | 无                        |
