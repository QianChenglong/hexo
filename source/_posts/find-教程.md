---
title: find-教程
categories: [linux]
tags: [linux, find, 教程]
date: 2015-02-13 10:22:18
---

# 格式

    find [where-to-find] [filter] [action]

所有参数都是可选的。

-   `where-to-find`，默认当前路径`.`
-   `filter`，默认为空，即不过滤
-   `action`，默认`-print`，向标准输出打印，换行符分隔

# 技巧

-   打印绝对路径

    -   windows

            find "%cd%"

    -   linux

            find "$PWD"


# 参考

1.  <http://content.hccfl.edu/pollock/Unix/FindCmd.htm>
1.  <http://linux.die.net/man/1/find>
