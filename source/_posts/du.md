---
title: du
categories: [linux]
tags: [linux, command, du]
date: 2015-06-18 09:23:02
---

# 功能

用来查看目录项磁盘使用情况。

# 常用选项

-   -a

    也输出文件，不只是目录

-   -h

    容易理解的格式输出

-   -s, --summarize

    等价于--max-depth=0，只输出本目录

-   --max-depth=N

    最大深度，与find一样

# 实例

-   只查看该文件或目录

        du -hs

-   查看目录的各目录项，不递归下去

        du -ah --max-depth=1

-   查看目录下*.c文件并排序输出到文件

        du --max-depth 1 -ah | grep '.*\.c' | sort -h > study

-   功能：方便的查看文件内存使用情况

        du -ah --max-depth=1 | sort -hr

