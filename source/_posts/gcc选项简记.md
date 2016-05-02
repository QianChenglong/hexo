---
title: gcc选项简记
categories: [gcc]
tags: [gcc, 选项]
date: 2015-02-05 11:26:51
---

-   -D name=definition

    指定预处理宏定义，相当于#define name definition

-   -std=XXX

    -   c99
    -   c++11

-   -M

    输出依赖关系，隐含-E，也就是不编译，只是查看依赖关系，依赖关系包含系统头文件

-   -MM

    输出依赖关系，只是用户的，不包含库文件

-   -MF file

    依赖关系的结果输出到指定文件中，必须指定-M或-MM

-   -MD

    相当于-MM -MF *.d ，
    输出依赖关系，不隐含-E，也就是同时生成依赖文件(*.d)，还编译,依赖关系中包含
    系统头文件

-   -MMD

   相当于-MD，生成的*.d中不包含系统头文件

-   -MT file

    使用file中的依赖关系编译，也就是配合-MMD或-MD或-MF来使用，使用他们生成的依赖
    关系自动编译

-   -MP

    连头文件也输出对应的依赖关系，可能为伪目标，防止删除了头文件，而没有更新
    makefile导致编译错误

-   -Ldir

    添加dir到目录列表，目录列表用来搜索链接库

-   -llibrary

    指定链接库，优先寻找共享库(liblibrary.so,liblibrary.a)，该选项最好放到最后，
    防止后面需要链接的，详见gcc(1)

-   -static

    指定链接静态库

-   -fPIC

    生成位置无关代码(position independent code)

-   -shared

    生成共享库，需要-fPIC

-   -Idir

    添加目录到搜索头文件列表，添加的优先搜索

-   -Wl,

    向链接器传递选项，','隔开选项

-   -Wa,

    向汇编器传递选项，','隔开选项

-   -Wp,

    向预处理器传递选项，','隔开选项

-   -O

    不开启优化
