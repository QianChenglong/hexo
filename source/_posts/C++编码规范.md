---
title: C++编码规范
categories: [C++]
tags: [C++, 编码规范]
date: 2014-12-16 10:51:34
---

# 目录组织

-   [3rdparty] 第三方包

-   [bin] 动态库或可执行文件生成目录

-   [cmake] cmake辅助

-   [doc] 文档

-   [include] 对外接口声明

    -   [库名称]

        -   [include]

-   [lib] 静态库生成目录

-   [src] 内部声明(*.h)，实现文件(*.c, *.cpp)

-   [test] 测试

参考：

1.  <http://stackoverflow.com/questions/2360734/whats-a-good-directory-structure-for-larger-c-projects-using-makefile?lq=1>
1.  <http://stackoverflow.com/questions/13967296/why-place-headers-in-a-separate-directory?lq=1>
1.  <http://stackoverflow.com/questions/1383174/source-file-organisation?lq=1>
1.  <http://stackoverflow.com/questions/1398445/directory-structure-for-a-c-library>

# 文件空行

-   `#pragma once`后空2行

-   `#include`模块间空1行

-   `#include`后空2行

-   函数定义间空1行

# 头文件

-   使用`#pragma once`

-   凡是能使用前向声明的，尽量使用，减少外部依赖！


## 头文件包含顺序

各部分最好按字母序排列

-   实现文件对应的头文件

    可以尽早发现该模块头文件中缺少的必须的头文件，使模块完全独立，不依赖于其他模块导入的头文件，减少了编译时间！

-   本模块下其他的头文件

-   C++库
-   C库
-   系统库

    确保该实现不依赖其他模块导入的头文件！

-   第三方库(根据使用广泛度，不同库换行)

-   本项目的其他模块头文件


**Note:**

-   若一些头文件依赖特定宏，则宏定义于头文件前
-   若头文件之间存在顺序问题，则可以不遵循

__参考__:

1.  <http://stackoverflow.com/questions/614302/c-header-order>
1.  <http://stackoverflow.com/questions/2762568/c-c-include-file-order-best-practices>

---

# 命名约定

## 文件命名

-   若是类文件，则与类名保持一致
-   若是C函数，则采用下划线分隔，因为本身C中就是用下划线分隔，不一致的话，在源码中如果涉及到该文件名，则可能需要转换规则
    如单元测试中，对`inet-helper.h`进行测试，则测试套件名需要转换。

## 变量命名

### 普通变量

下划线分隔

### 成员变量

下划线分割，添加后缀'_'

## 常量命名

前缀`k`，骆驼命名，如`kDaysInWeek`

## 函数命名

### 普通函数

函数名以小写骆驼命名，如`isEmpty()`

### 存取函数

下划线分隔，如`get_num()`

## 宏命名

大写，下划线分隔

---

# 类

## 类组织

-   `public`，成员函数

-   `public`，静态函数

-   `private`，宏定义

-   `private`，类型定义

-   `private`，内部成员函数

-   `private`，静态数据成员定义

-   `private`，数据成员定义

---

# 参考

1.  <http://google-styleguide.googlecode.com/svn/trunk/cppguide.html>
1.  <http://www.c-xx.com/ccc/ccc.php>
1.  <https://en.wikipedia.org/wiki/Underscore>
1.  <https://en.wikipedia.org/wiki/Naming_convention_(programming)>
1.  <https://en.wikipedia.org/wiki/Hyphen>
