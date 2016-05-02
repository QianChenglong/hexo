---
title: syslinux
categories: [syslinux]
tags: [syslinux]
date: 2015-03-20 15:21:26
---

# syslinux安装

-   安装时，会将`ldlinux.c32`,`ldlinux.sys`拷贝到安装目录，默认为`boot/syslinux/`，
    可以使用`--directory  -d  Directory for installation target`指定

    syslinux安装的分区上的PBR会根据安装目录查找`ldlinux.c32`，并将该目录作为根目录

# syslinux引导过程

-   MBR加载活动分区PBR

-   PBR根据安装时指定的安装目录，查找`ldlinux.c32`，若找不到，则到根目录查找

-   查找读取`syslinux.cfg`

-   进入菜单交互


# syslinux文件说明

| 文件名       | 功能                        | 依赖                     |
|--------------+-----------------------------+--------------------------|
| ldlinux.c32  | 查找、解析syslinux.cfg      |                          |
| libutil.c32  | 功能库                      |                          |
| libcom32.c32 | 核心功能库                  |                          |
| vesamenu.c32 | 菜单功能                    | libutil.c32,libcom32.c32 |
| splash.jpg   | 图片背景                    |                          |
| syslinux.cfg | 启动配置文件                |                          |
| chain.c32    | 链式加载                    |                          |
| memdisk      | `memdisk`命令，虚拟内存磁盘 |                          |
| hdt.c32      | 硬件检测工具                | libmenu.c32,libgpl.c32   |
| linux.c32    | `linux`命令                 |                          |

# note

-   启动ISO镜像

    因为image都是通过虚拟设备(虚拟软盘，虚拟光驱)，由BIOS 13号中断来访问的，
    所以当操作系统加载完设备驱动时，它将自己去访问设备，不再通过BIOS去访问，
    这时虚拟设备将失效，报错`INT 13h access: Not all images will complete the boot process!`

# 参考

1.  <http://www.syslinux.org/wiki/index.php/Syslinux_5_Changelog>
1.  <http://www.syslinux.org/wiki/index.php/Library_modules>
1.  <http://linux.die.net/man/1/syslinux>
1.  <http://www.syslinux.org/wiki/index.php/SYSLINUX>
1.  <http://www.syslinux.org/wiki/index.php/Boot_an_Iso_image>
1.  <http://www.syslinux.org/wiki/index.php/MEMDISK#INT_13h_access:_Not_all_images_will_complete_the_boot_process.21>
1.  <http://www.syslinux.org/wiki/index.php/MEMDISK>
