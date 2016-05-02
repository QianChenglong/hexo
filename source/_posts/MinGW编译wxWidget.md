---
title: MinGW编译wxWidget
categories: [MinGW]
tags: [MinGW, wxWidget]
---

- WXWIN：源代码根目录

1. 解压源码

2. 进入到`%WXWIN%\build\msw`

3. 清理项目

        mingw32-make -f makefile.gcc SHARED=1 UNICODE=1 BUILD=release clean

4. 编译

- 动态库，发行版

        mingw32-make -f makefile.gcc SHARED=1 UNICODE=1 BUILD=release

- 动态库，调试版

        mingw32-make -f makefile.gcc SHARED=1 UNICODE=1 BUILD=debug

- 静态库，发行版

        mingw32-make -f makefile.gcc SHARED=0 UNICODE=1 BUILD=release

- 静态库，调试版

        mingw32-make -f makefile.gcc SHARED=0 UNICODE=1 BUILD=debug

    **注**:

    1. 可以添加-j N(N指当前CPU核心数)，加快编译速度

    2. 每种版本可以根据需要编译

    3. 动态库对应的目录(%WXWIN%\lib\gcc_dll)，静态库对应的目录(%WXWIN%\lib\gcc_lib)

    4. Debug版的库名称会有`d`后缀，UNICODE版的库名称会有`u`后缀
