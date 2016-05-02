---
title: linux-禁用IPv6
categories: [linux]
tags: [linux, IPv6]
date: 2015-03-09 14:57:39
---

# 通过`procps`

-   修改`/etc/sysctl.conf`

        net.ipv6.conf.all.disable_ipv6 = 1

-   重新读取

        sysctl -wp

# 通过boot loader

-   修改配置文件

    -   syslinux

            /boot/syslinux/syslinux.cfg

    -   grub

            /boot/grub/grub.cfg

-   在内核启动参数添加

        ipv6.disable=1
