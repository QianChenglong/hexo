---
title: column
categories: [linux]
tags: [linux, command, column]
date: 2015-06-18 09:56:35
---

# 功能

将记录表格化输出

# 常用选项

-   -s

    指定分隔字符【集】，如',;'

-   -t

    表格化打印

# 实例

-   查看最近1天内修改过的文件，表格化打印

        find . -mtime -1|xargs stat -c"%n,%.19y"|column -s, -t
