---
title: centos-安装virtualbox增强功能
categories: [virtualbox]
tags: [virtualbox, centos]
date: 2015-06-17 17:37:23
---

# 环境

-   CentOS-7.0.1

-   VirtualBox-4.3.28

# 步骤

1.  更新内核

    yum update kernel
    reboot

1.  安装依赖

        rpm -Uvh http://dl.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-5.noarch.rpm
        yum install gcc kernel-devel kernel-headers dkms make bzip2 perl

1.  在虚拟机控制器中，添加`VBoxGuestAdditions.iso`

1.  挂载光盘

        mkdir /mnt/cdrom
        mount /dev/cdrom /mnt/cdrom

1.  编译安装

        cd /mnt/cdrom && ./VBoxLinuxAdditions.run

1.  重启生效

        reboot

# 参考

1.  <http://www.if-not-true-then-false.com/2010/install-virtualbox-guest-additions-on-fedora-centos-red-hat-rhel/comment-page-7/>
