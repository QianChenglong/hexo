---
title: od
categories: [od]
tags: [od]
date: 2015-02-27 16:01:17
---

# 选项

-   -t TYPE

    指定输出格式，
    TYPE由进制和多少字节组合决定，如x1，则以十六进制，每次输出1字节

    -   a named character
    -   c ASCII character or backslash escape
    -   d signed decimal
    -   f floating point
    -   o octal
    -   u unsigned decimal
    -   x hexadecimal
    -   C char
    -   S short
    -   I int
    -   L long
    -   For floating point (f):
    -   F float
    -   D double
    -   L long double

-   -w BYTES

    指定一行的宽度

-   -A, --address-radix=radix

    指定文件偏移量显示的基数(d,o,x)

-   -j, --skip-bytes=BYTE

    从BYTE（文件偏移量）开始显示

-   -c

    把元素的内容按照ASCII码解释成对应的字符

# 实例

-   十六进制，按字节输出，并输出对应的ASCII字符

        od -t x1 -c foo

-   同时按几种方式输出

        od -tx1 -tc foo

-   跳过指定字节

        od -Ax -tx1 -tc -j 0x065c main |less

