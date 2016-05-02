---
title: BSD-tcp-ip头文件组织
categories: [网络]
tags: [网络, tcp-ip]
date: 2015-02-04 11:56:28
---

| 头文件           | 作用                                             |
|------------------+--------------------------------------------------|
| `<sys/socket.h>` | 核心socket API和数据结构                         |
| `<netinet/in.h>` | IPv4，IPv6等相关协议族地址结构定义，常用端口定义 |
| `<arpa/inet.h>`  | IP地址操作                                       |
| `<netdb.h>`      | 网络数据库查询，如主机名，服务等                 |


# 参考

1.  <http://en.wikipedia.org/wiki/Berkeley_sockets#Header_files>
