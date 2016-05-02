---
title: C-函数操作结果返回方式
categories: [C]
tags: [C]
date: 2015-03-26 15:44:29
---

# 通过返回值

## 直接值传递

### 优点

简单，快捷，不存在内存溢出

### 缺点

-   不能返回错误代码

-   无法返回非内置数据类型

### 适用范围

-   返回简单的内置类型数据

-   出错少或错误不是很严重

### 实例

    size_t strlen(const char * str);

## 内部分配static类型数据，返回指针

### 优点

-   可返回非内置数据类型

-   调用方便，调用者无需手动分配内存

### 缺点

-   不可重入

-   非线程安全

### 实例

    char *inet_ntoa(struct in_addr);

# 通过参数

## 调用者分配内存，需要传入缓冲区大小

### 优点

-   可返回非内置数据类型

-   可重入

-   线程安全

-   正确操作下，内存不会溢出(通过缓冲区大小参数)

### 缺点

-   调用麻烦，需要手动分配内存

### 实例

    char* fgets(char *str, int num, FILE * stream);

## 调用者分配，不传入缓冲区大小(自己不采用，只是存在此种接口)

### 优点

-   可返回非内置数据类型

-   可重入

-   线程安全

### 缺点

-   存在缓冲区越界风险！


### 实例

    char * gets ( char * str );

## 二次调用确定所需空间

### 优点

-   可以返回调用者不能确定的内存空间的数据

### 缺点

-   二次调用，使用麻烦

### 实例

    DWORD GetAdaptersInfo(_Out_    PIP_ADAPTER_INFO pAdapterInfo, _Inout_  PULONG pOutBufLen);

# 参考

1.  [GetAdaptersInfo](https://msdn.microsoft.com/zh-cn/library/windows/desktop/aa365917(v=vs.85).aspx)
