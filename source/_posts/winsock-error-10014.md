---
title: winsock-error-10014
categories: [winsock]
tags: [winsock, error, recvfrom, 10014]
date: 2015-01-20 14:48:28
---

# 错误代码

```cpp
if (recvfrom(socket, recv_buf, sizeof(recv_data), 0, (sockaddr *)&server_addr, NULL) == SOCKET_ERROR) {
    WinSock::printError("recvfrom error");
    return false;
}
```

# 原因

`recvfrom`最后一个参数是指定socket地址，为传入传出参数，不能为`NULL`!

# 解决

```cpp
int len = sizeof(server_addr);
if (recvfrom(socket, recv_buf, sizeof(recv_data), 0, (sockaddr *)&server_addr, &len) == SOCKET_ERROR) {
    WinSock::printError("recvfrom error");
    return false;
}
```

# 参考

1.  <http://stackoverflow.com/questions/17306405/c-udp-recvfrom-is-acting-strange-wsagetlasterror-10014>
