---
title: gdb
tags: [gdb]
date: 2015-08-04 14:05:47
---

# etc

-   自定义初始化设置

        ~/.gdbinit

-   载入配置文件

        source ~/.gdbinit

# 启动

-   使用core调试

        gdb -c <core-file-name> <program>

-   attach到指定进程

        gdb -p <pid>
        gdb attach <pid>

# 控制类

-   运行到指定行

        until $line-number

-   向上栈

        up <num>

# 断点

-   在指定文件指定行

        break filename:linenum

-   删除断点

        clear linenum

# 查询类

-   打印调用栈

        bt
        where

-   打印当前帧(查询当前执行语句位置)

        frame

-   打印当前行

        list *$pc

-   x(examine)

        x /[nfu] ADDRESS(若ADDRESS是一个变量，则认为变量值为要查看的地址)
        n用来指定重复的次数，就是指定显示格式和size确定的一个单位多少次
        #n默认为1

        f用来指定显示的格式，同print一样
            Format letters
            o(octal), x(hex), d(decimal), u(unsigned decimal), t(binary),
            f(float), a(address), i(instruction), c(char) and s(string)
        u(unit)，指定一个单位的长度
            Size letters
            b(byte), h(halfword, 2B), w(word, 4B), g(giant, 8 bytes)

        x/3uh 0x54320
            从0x54320开始，以(h)2B为单位，(u)无符号十进制输出，显示3uh个这样的单
            位，总共显示2 × 3 = 6B的内存

        x /10s *argv    查看环境变量

# set

-   set args ARG-list

    设置程序的命令行参数，依次传给argv[1],...
    #需要在文件载入之后，程序开始执行之前

-   set print pretty

    可爱的打印出结构体

# gdb打印STL<https://sourceware.org/gdb/wiki/STLSupport>
