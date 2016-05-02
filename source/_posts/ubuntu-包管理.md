---
title: ubuntu-包管理
categories: [ubuntu]
tags: [ubuntu, 包管理, apt]
date: 2015-02-03 17:05:51
---

# apt-get

-   只下载不安装(二进制包)

        apt-get download PACKAGE

-   下载源代码

        apt-get source PACKAGE

# apt-cache

-   查询包依赖(该包依赖哪些包)

        apt-cache depends PACKAGE

-   查询反向依赖(哪些包依赖该包)

        apt-cache rdepends PACKAGE

-   查询包信息(基本信息，依赖信息)

        apt-cache showpkg PACKAGE
        apt-cache show PACKAGE

-   查看包版本

        apt-cache policy PACKAGE

-   搜索包

        apt-cache search PATTERN

# apt-file(需要安装)

-   列出包文件列表

        apt-file list PACKAGE
