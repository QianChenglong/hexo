---
title: arch-安装纪录
categories: [arch]
tags: [arch]
date: 2015-06-24 18:35:26
---

# 建立网络连接

## 有线

### 默认开启了dhcpcd服务

1.  检查网络状态

        ping jd.com

### 若DHCP失败静态分配IP

1.  查看以太网接口名

        ip link

1.  启动网络接口

        ip link set <interface-name> up

1.  添加IP

        ip addr add <ip-address>/<mask-bits> dev <interface-name>

1.  添加网关

        ip route add default via <gateway-ip>

1.  配置DNS

        vim /etc/resolv.conf

        nameserver 8.8.8.8

## WIFI

1.  查看网卡接口

        iwconfig

1.  启动网卡接口

        ip link set <interface-name> up

1.  连接网络

        wifi-menu <interface-name>

# 磁盘分区

-   硬盘分区

        cfdisk /dev/sda

-   格式化分区

        mkfs.ext4 /dev/sdaX

-   挂载分区

        mount /dev/sdaX /mnt

# 安装

-   修改软件源

        vi  /etc/pacman.d/mirrorlist

        Server = http://mirrors.163.com/archlinux/$repo/os/$arch

-   安装基本系统

        pacstrap /mnt base base-devel

-   生成fstab

        genfstab -U -p /mnt >> /mnt/etc/fstab

# 系统配置

chroot到新系统

    arch-chroot /mnt

## locale

1.  启用locale

        vi /etc/locale.gen

        en_US.UTF-8 UTF-8
        zh_CN.GB18030 GB18030
        zh_CN.GBK GBK
        zh.CN.UTF-8 UTF-8
        zh_CN GB2312

1.  生成本地语言

        locale-gen

1.   [设置系统默认语言]

        vi /etc/locale.conf

        LANG=zh_CN.UTF-8
        LC_TIME=en_GB.UTF-8

## 时间

1.  设置时区

        echo Asia/Shanghai >/etc/timezone

1.  链接时区

        ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

1.  系统时间保存到bios

        hwclock --systohc --localtime

##  主机名

    echo Arch >/etc/hostname

##  创建初始ramdisk环境

    mkinitcpio -p linux

##  设置Root密码并创建一般用户

    passwd
    useradd -m  -s /bin/bash qian
    passwd qian

## 启动加载器

-   grub[优先]

        pacman -S　grub-biso os-prober
        grub-install --target=i386-pc --recheck /dev/sda
        grub-mkconfig -o /boot/grub/grub.cfg

-   syslinux

    1.  安装

            pacman -S syslinux
            syslinux-install_update -ima

    1.  配置

            vi /boot/syslinux/syslinux.cfg

## 配置网络

-   配置无线

    pacman -S wierless_tools wpa_supplicant wpa_actiond dialog

-   配置有线

    -   dhcp

        -   通过dhcpcd服务

                systemctl enable dhcpcd@interface_name.service

        -   通过netctl

                cd /etc/netctl
                cp examples/ethernet-dhcp my_network
                vi my_network(修改接口名称)
                netctl enbale my_network

## 安装图形界面

-   安装Xorg和gnome

        pacman -S　xorg gnome

-   开机自动启动GUI

        systemctl enable gdm.service
