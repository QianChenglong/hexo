---
title: virtualbox-拓展磁盘空间
categories: [virtualbox]
tags: [virtualbox, 磁盘]
date: 2015-02-09 10:44:04
---

# 环境

-   宿主    win7-64

-   虚拟机  ubuntu-14.04

# 步骤

1.  进入`virtualbox`目录

1.  调整大小

        VBoxManage.exe modifyhd E:\Soft\VirtualBox\VMs\Ubuntu-14.04\Ubuntu-14.04.vdi --resize 20480

1.  重新调整分区大小

    -   使用`GParted Live CD`

    -   使用`ubuntu Live CD`

# 参考

1.  <https://forums.virtualbox.org/viewtopic.php?f=35&t=50661>
