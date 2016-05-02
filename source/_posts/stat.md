---
title: stat
categories: [linux]
tags: [linux, command, stat]
date: 2015-06-18 09:31:36
---

# 功能

查看文件信息

# 常用选项

-   -c  --format=FORMAT

    -   %n 文件名

    -   %y 修改时间，易读格式


# 实例

-   指定显示文件修改时间长度

        find . -mtime -1|xargs stat -c"%n %.19y"|column -t
