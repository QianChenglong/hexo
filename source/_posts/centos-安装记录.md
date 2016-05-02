---
title: centos-安装记录
tags: [centos]
date: 2016-04-13 18:27:28
---

-   安装VBoxGuestAdditions

-   配置sudo

        visudo

        wallace ALL=(ALL)       NOPASSWD: ALL

-   安装epel(<http://www.cyberciti.biz/faq/installing-rhel-epel-repo-on-centos-redhat-7-x/>)

        yum install epel-release

-   添加组

        yum install libuser
        lgroup -M wallace vboxsf

-   配置环境变量

        vi /etc/profile

-   配置系统语言

        echo LANG=en_US.UTF-8 >/etc/locale.conf

-   配置启动时间

        vi /boot/grub2/grub.cfg

        set timeout=1
