---
title: 运行python脚本出错-No such file or directory
categories: [python]
tags: [python]
date: 2015-01-29 13:25:25
---

# 原因

文件格式为`DOS`格式，`#! /usr/bin/env python`后有`\r\n`，而`/usr/bin/env`的参数为`python\r`，
找不到即报改错；因为有`\r`在`python`输出后回到行首继续打印，则导致

`: No such file or directory`

# 解决

文件格式改为`UNIX`格式

# 参考

1.  <http://hgoldfish.com/blogs/article/31/>
1.  <http://stackoverflow.com/questions/12996065/no-such-file-or-directory>
