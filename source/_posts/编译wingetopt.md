---
title: 编译wingetopt
categories: [wingetopt]
tags: [getopt, wingetopt, cmake]
date: 2014-12-11 14:24:44
---

# 环境

-   VS2010

# 步骤

-   下载[QianChenglong/wingetopt](https://github.com/QianChenglong/wingetopt)

-   新建`build`，并进入

-   生成`Makefile`

    -   debug

            cmake -G "NMake Makefiles" -DCMAKE_BUILD_TYPE=Debug -DCMAKE_INSTALL_PREFIX=./wingetopt ..

    -   release

            cmake -G "NMake Makefiles" -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=./wingetopt ..

-   编译

        nmake

-   安装

        nmake install
