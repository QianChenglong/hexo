---
title: openwrt-开启ssh
categories: [openwrt]
tags: [openwrt, ssh]
date: 2015-02-11 11:53:50
---

1.  编辑配置文件

        vi /etc/config/dropbear

1.  添加

        option enable '1'

1.  重启

        reboot
