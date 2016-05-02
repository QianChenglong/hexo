---
title: log4cpp编译安装
date: 2014-11-11
categories: log4cpp
tags: [log4cpp, 编译]
---

## 下载

[官网](http://sourceforge.net/projects/log4cpp/files/)

## 编译

-   解压
-   找到对应工程配置文件(vs2010:msvc10)
-   打开msvc10.sln
-   生成log4cppLIB(静态库版本)，debug版和release版
-   新建目标目录如`log4cpp-1.1.1`
-   将`include`目录复制到目标目录下
-   将生成的lib(`log4cppD.lib`,`log4cppLIB.lib`)放到目标目录的子目录`lib`

最终目录结构：

    └─log4cpp-1.1.1
        ├─include
        │  └─log4cpp
        │
        └─lib

## 配置解决方案属性

-   【VC++目录】，添加`include`目录和`lib`目录
-   Debug版，添加【附加依赖项】，`log4cppD.lib`
-   Release版，添加【附加依赖项】，`log4cppLIB.lib`
