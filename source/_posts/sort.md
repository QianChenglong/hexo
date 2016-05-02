---
title: sort
categories: [linux]
tags: [linux,command,sort]
date: 2015-06-18 08:52:36
---

# 工作流程

sort将文件的每一行作为一个单位，相互比较，比较原则是从首字符向后，依次按ASCII码值进行比较，最后将他们按升序输出。

# 常用选项

-   -b

    忽略前导空白

-   -d

    用来排序目录，只考虑空白符和字符？

-   -n

    根据字符串形式对应的数字排序

-   -h

    根据易读格式排序，也就是使用了B,K,M等

-   -r

    结果逆序输出

-   -s

    稳定排序

-   -u

    去除键重复的记录

-   -o FILENAME

    输出到指定文件，避免重定向到同一文件时造成的内容截断

-   -t, --field-separator=SEP

    使用指定分隔符来分割记录

-   -k, --key=KEYDEF

    指定排序键，可以多次指定

# 实例

-   按第3字段的数字值排序输出

        cat /etc/passwd|sort -t':' -n -k3,3 |less
