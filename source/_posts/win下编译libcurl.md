---
title: win下编译libcurl
date: 2014-12-10
categories: [curl]
tags: [curl, libcurl, windows, 编译]
---

## 环境

-   VS2010
-   [openssl-1.0.1j](https://www.openssl.org/source/)
-   curl-7.39.0

## 编译

-   下载[官网](http://curl.haxx.se/)，解压

-   将**编译好的**`openssl`({ iLink title:win下编译openssl %})拷贝到`../deps`

    ![](/img/win下编译libcurl_01.png)

-   进入`winbuild`目录

-   编译(具体参考`winbuild/BUILD.WINDOWS.txt`)

    -   release

        nmake /f Makefile.vc mode=dll VC=10 WITH_SSL=dll ENABLE_IDN=no

    -   debug

        nmake /f Makefile.vc mode=dll VC=10 WITH_SSL=dll ENABLE_IDN=no DEBUG=yes

-   输出目录为`builds`

    ![](/img/win下编译libcurl_02.png)
