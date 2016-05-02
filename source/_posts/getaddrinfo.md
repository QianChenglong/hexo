---
title: getaddrinfo
categories: [socket]
tags: [socket, API, getaddrinfo]
date: 2015-02-05 15:02:53
---

# 原型

```c
int getaddrinfo(const char *node, const char *service,
                       const struct addrinfo *hints,
                       struct addrinfo **res);
```

# 功能

-   转换主机名到IP地址(IPv4，IPv6)
-   转换服务到端口
-   不要用来查询本机IP，其只返回`127.0.0.1`

# 特色

-   使用`hints`来控制输出参数

# 参考

1.  <http://pubs.opengroup.org/onlinepubs/9699919799/functions/freeaddrinfo.html>
1.  <http://man7.org/linux/man-pages/man3/getaddrinfo.3.html>
1.  <http://beej-zhtw.netdpi.net/05-system-call-or-bust/5-1-getaddrinfo-start>
