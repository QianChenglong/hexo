---
title: linux-ps
tags: [linux, ps]
date: 2015-09-01 11:16:40
---

# 说明

-   破折号开头的为UNIX风格

-   不带破折号开头的为BSD风格

-   gnu long option，双破折号开头

# 选项

-   -e

    同`-A`完全一样，选择所有进程

-   -f

    输出所有信息

-   -j

    jobs格式，输出`PGID   SID  C STIME`

**OUTPUT MODIFIERS**

-   --forest

    进程树

# 实例

-   查看当前用户进程

        ps -f
