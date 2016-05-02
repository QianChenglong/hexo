---
title: jsoncpp编译安装
date: 2014-12-09
categories: jsoncpp
tags: [jsoncpp, 编译]
---

## 前提

-   VC++(_改用其他编译器，下面的Makefile需要改成对应的_)
-   cmake

## 编译

-   下载[官网](https://github.com/open-source-parsers/jsoncpp)

-   解压，在根目录新建`build`目录

-   [可选]`debug`库添加`d`后缀

    编辑根目录下`CMakelists.txt`，添加一行

        SET(CMAKE_DEBUG_POSTFIX d)

-   `cd build`

-   生成`makefile`

    -   shared-debug

            cmake -DCMAKE_BUILD_TYPE=debug -DJSONCPP_LIB_BUILD_SHARED=ON -DCMAKE_INSTALL_PREFIX=./jsoncpp-0.7.0-shared-debug -G "NMake Makefiles" ..

    -   shared-release

            cmake -DCMAKE_BUILD_TYPE=release -DJSONCPP_LIB_BUILD_SHARED=ON -DCMAKE_INSTALL_PREFIX=./jsoncpp-0.7.0-shared-release -G "NMake Makefiles" ..

    -   static-debug

            cmake -DCMAKE_BUILD_TYPE=debug -DJSONCPP_LIB_BUILD_SHARED=OFF -DCMAKE_INSTALL_PREFIX=./jsoncpp-0.7.0-static-debug -G "NMake Makefiles" ..

    -   static-release

            cmake -DCMAKE_BUILD_TYPE=release -DJSONCPP_LIB_BUILD_SHARED=OFF -DCMAKE_INSTALL_PREFIX=./jsoncpp-0.7.0-static-release -G "NMake Makefiles" ..
-   编译

        nmake

-   安装

        nmake install

-   生成`doxygen`文档

        python doxybuild.py --doxygen="d:\Program Files\doxygen\bin\doxygen.EXE" --open

# 问题

-   为什么使用`nmake`(`/MT`)和`vs2010`(`/MD`)编译链接的C运行库版本不一致？

## 参考

1.  <https://github.com/open-source-parsers/jsoncpp>
