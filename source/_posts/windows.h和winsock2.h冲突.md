---
title: windows.h和winsock2.h冲突
date: 2014-12-04
categories: windows
tags: [windows.h, winsock2.h, socket]
---

## 原因

```c
#include <windows.h>
#include <winsock2.h>
```
-   在包含`WinSock2.h`之前包含了`Windows.h`
-   而`Windows.h`包含了`WinSock.h`
-   而`WinSock.h`和`WinSock2.h`不兼容！

## 解决方案

-   第一种(**优先使用**)

```c
#include <winsock2.h>
#include <windows.h>
```

-   第二种

```c
#define WIN32_LEAN_AND_MEAN
#include <windows.h>
#include <winsock2.h>
```
