---
title: tcp-accept
tags: [tcp, accept]
date: 2016-03-11 16:31:20
---

```c
int accept(int socket, struct sockaddr *restrict address,
           socklen_t *restrict address_len);
```

# 要点

-   `address_len`为传入传出参数！

-   当监听套接字设置为非阻塞时，若`accept`未获取到连接，则不阻塞，返回失败，`errno`设置为`EAGAIN`或`EWOULDBLOCK`

# 错误代码

-   `EMFILE` 打开的文件超过限制
