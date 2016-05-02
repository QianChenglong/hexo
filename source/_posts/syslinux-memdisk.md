---
title: syslinux-memdisk
categories: [syslinux]
tags: [syslinux, memdisk]
date: 2015-03-23 11:11:03
---

# 作用

启动一些软盘镜像，硬盘镜像，ISO镜像。

# 如何使用

memdisk作为`kernel`，而那些镜像文件作为初始化文件系统(initrd)

镜像文件(zip或gzip格式)作为`INITRD`命令的参数传递

-   命令行方式

    memdisk initrd=hdt.img

-   配置文件方式

        # Boot Hardware Detection Tool from floppy image
        LABEL hdt_floppy
        LINUX memdisk
        INITRD hdt.img

        # Boot Hardware Detection Tool from iso image (with 'iso' parameter)
        LABEL hdt_iso
        LINUX memdisk
        INITRD hdt.iso
        APPEND iso

        # Boot DOS from floppy image (with 'raw' parameter)
        LABEL dos_floppy_with_raw
        LINUX memdisk
        INITRD dosboot.img
        APPEND raw

# 参考

1.  <http://www.syslinux.org/wiki/index.php/MEMDISK>
