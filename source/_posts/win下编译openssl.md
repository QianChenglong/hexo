---
title: win下编译openssl
date: 2014-12-10
categories: openssl
tags: [openssl, windows, 编译]
---

## 前提

-   perl
-   VC++

## 编译(详细过程参考`INSTALL.W32`)

-   生成`Makefile`

        perl Configure VC-WIN32 no-asm --prefix=c:/some/openssl/dir
        ms\do_ms

-   编译

        nmake -f ms\ntdll.mak

-   测试

         nmake -f ms\ntdll.mak test

-   安装

        nmake -f ms\ntdll.mak install
