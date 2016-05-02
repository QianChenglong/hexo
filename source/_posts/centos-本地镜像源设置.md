---
title: centos-本地镜像源设置
categories: [centos]
tags: [centos]
date: 2015-05-30 14:32:16
---

-   挂载镜像文件

        mkdir /mnt/cdrom
        mount /dev/cdrom /mnt/cdrom

-   编辑repo文件

        vim /etc/yum.repos.d/centos7-local.repo

        [local]
        name=local
        baseurl=file:///mnt/cdrom
        enabled=1
        gpgcheck=1
        gpgkey=file:///mnt/cdrom/RPM-GPG-KEY-CentOS-7
