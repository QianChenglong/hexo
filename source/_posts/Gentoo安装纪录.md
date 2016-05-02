---
title: Gentoo安装纪录
categories: [gentoo]
tags: [gentoo, 安装]
date: 2015-02-11 16:52:17
---

# 安装环境配置

-   [官网镜像下载](https://www.gentoo.org/main/en/where.xml)

-   配置镜像从启动

-   按**F1**进入`kernel`选择

-   输入`gentoo`，启动

# 配置网络

-   查看网络

        ifconfig

-   若自动配置失败，执行`net-setup`，在选择`DHCP`即可

# 磁盘分区

-   分区规划

    /dev/sda1   boot    128M    ext2
    /dev/sda2   swap    512M    swap
    /dev/sda3   root    剩余    ext4

-   格式化分区

        mkfs.ext2 /dev/sda1
        mkswap /dev/sda2
        mkfs.ext4 /dev/sda3

-   启用swap分区

        swapon /dev/sda2

-   挂载分区

        mount /dev/sda3 /mnt/gentoo
        mkdir /mnt/gentoo/boot
        mount /dev/sda1 /mnt/gentoo/boot

# 安装stage

-   设置当前时间

        date MMDDhhmmYYYY

-   `cd /mnt/gentoo`

-   下载stage3压缩包(选择就近mirror)

        links http://www.gentoo.org/main/en/mirrors.xml

-   解压

        tar xvjpf stage3*

-   修改编译控制文件

        vi /mnt/gentoo/etc/portage/make.conf


        CFLAGS="-march=native -O2 -pipe"

        MAKEOPTS="-j2"

# 安装基本系统

## Chrooting

-   设置镜像源

        vi /mnt/gentoo/etc/portage/make.conf

        SYNC="rsync://mirrors.ustc.edu.cn/gentoo-portage/"
        GENTOO_MIRRORS="http://mirrors.aliyun.com/gentoo/"

-   复制DNS信息

        cp -L /etc/resolv.conf /mnt/gentoo/etc/

-   挂载文件系统

        mount -t proc proc /mnt/gentoo/proc
        mount --rbind /sys /mnt/gentoo/sys
        mount --make-rslave /mnt/gentoo/sys
        mount --rbind /dev /mnt/gentoo/dev
        mount --make-rslave /mnt/gentoo/dev

-   进入新环境

        chroot /mnt/gentoo /bin/bash
        source /etc/profile
        export PS1=“(chroot) $PS1”

## 配置portable

-   安装portage快照

        emerge-websync

-   更新portage tree

        emerge --sync

-   配置时区

        echo "Asia/Shanghai" >/etc/timezone
        emerge --config sys-libs/timezone-data

-   配置locales

    -   编辑

            nano /etc/locale.gen


            en_US.UTF-8 UTF-8
            zh_CN.UTF-8 UTF-8

    -   生成locale

            locale-gen

    -   选择默认locale

            eselect locale list
            eselect locale set 3

#   配置内核

-   安装源码

        emerge --ask sys-kernel/gentoo-sources

-   手动配置

        cd /usr/src/linux
        make menuconfig

-   编译安装

        make && make modules_install
        make install

# 配置系统

## 文件系统

-   编辑fstab

        nano -w /etc/fstab

# 网络信息

-   hostname

        nano -w /etc/conf.d/hostname


        hostname="long"

# 参考

1.  <https://wiki.gentoo.org/wiki/Handbook:AMD64>
1.  <http://www.gentoo.org/doc/zh_cn/gentoo-x86-quickinstall.xml>
1.  <https://www.youtube.com/watch?v=P1ok-3z14ss>
