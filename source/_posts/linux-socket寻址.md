---
title: linux-socket寻址
categories: [linux]
tags: [linux, socket, sockaddr, sockaddr_in, in_addr]
date: 2015-02-03 18:00:50
---

# 环境

-   ubuntu-14.04

-   glic-2.19

-   工作目录：`/usr/include`

# 数据结构

## `struct sockaddr`

`socket`API接口，无关具体地址族，协议。

### 定义位置

`x86_64-linux-gnu/sys/socket.h` => `x86_64-linux-gnu/bits/socket.h`

```c
/* Structure describing a generic socket address.  */
struct sockaddr
  {
    __SOCKADDR_COMMON (sa_);    /* Common data: address family and length.  */
    char sa_data[14];       /* Address data.  */
  };
```

**Note:**

-   `=>`表示包含

## `strcut sockaddr_in`

具体类型数据结构，用来操作地址族，IP，端口。

### 定义位置

`netinet/in.h`

```c
/* Structure describing an Internet socket address.  */
struct sockaddr_in
  {
    __SOCKADDR_COMMON (sin_);
    in_port_t sin_port;         /* Port number.  */
    struct in_addr sin_addr;        /* Internet address.  */

    /* Pad to size of `struct sockaddr'.  */
    unsigned char sin_zero[sizeof (struct sockaddr) -
               __SOCKADDR_COMMON_SIZE -
               sizeof (in_port_t) -
               sizeof (struct in_addr)];
  };
```

## `struct in_addr`

定义IP

### 定义位置

`netinet/in.h`

```c
/* Internet address.  */
typedef uint32_t in_addr_t;
struct in_addr
  {
    in_addr_t s_addr;
  };
```

# 关系

`in_addr` => `sockaddr_in` => `sockaddr`

**Note**:

-   `=>`表示构成

# 说明

## socket地址结构传递方向

-   从进程到内核

    需要传入参数(套接字地址大小，告诉内核需要复制多少字节)

    -   bind
    -   connect
    -   sendto
    -   sendmsg

-   从内核到进程

    需要传入传出参数(套接字地址大小，告诉内核需要复制多少字节，以及反馈进程，返回的地址结构大小)

    -   accept
    -   recvfrom
    -   recvmsg
    -   getpeername
    -   getsockname
