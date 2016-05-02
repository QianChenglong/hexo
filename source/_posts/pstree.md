---
title: pstree
tags: [pstree]
date: 2016-03-23 10:13:19
---

# 选项

-   -a

    输出进程的命令行参数

-   -p

    输出进程PID

-   -u

    输出进程使用者

-   -s

    Show parent processes of the specified process.

-   -n

    按PID排序

-   -l

    完整显示，默认80列

-   -h

    高亮当前进程及其父进程

-   -H PID

    高亮PID进程及其父进程


# 实例

-   显示PID进程的族谱

        pstree -apls PID
