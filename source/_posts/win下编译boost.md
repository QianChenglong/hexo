---
title: win下编译boost
categories: [boost]
tags: [windows, boost, 编译]
date: 2015-1-23 13:36:34
---

# 环境

-   VS2010
-   boost-1.57.0

# 编译Boost

1.  [官网](http://www.boost.org/)下载源码

1.  解压文件

1.  进入根目录

1.  运行配置工具生成文件

    -   Windows:bootstap.bat

    -   Linux:bootstrap.sh

1.  编译，安装

    -   VS2005

            bjam --toolset=msvc-8.0 --prefix=D:\Boost_XXX --build-type=complete install

    -   VS2008

            bjam --toolset=msvc-9.0 --prefix=D:\Boost_XXX --build-type=complete install
    -   VS2010

            bjam --toolset=msvc-10.0 --prefix=D:\Boost_XXX --build-type=complete install

    -   VS2012

            bjam --toolset=msvc-11.0 --prefix=D:\Boost_XXX --build-type=complete install

**Note:**

-   清除

        bjam.exe --clean

# 使用

1.  配置IDE

    ![头文件](/img/win下编译boost-01.png)
    ![库文件](/img/win下编译boost-02.png)
