---
title: samba-常用操作
categories: [samba]
tags: [samba, 操作]
date: 2015-02-10 10:39:55
---

-   测试配置文件语法

        testparm

-   本地连接测试

        smbclient -L //127.0.0.1

-   观察连接状态

        smbstatus

-   挂载共享目录

        mount -t cifs //127.0.0.1/read /mnt

-   查看用户

        pdbedit -L

-   添加一个用户

        pdbedit -a -u USERNAME

-   删除用户

        pdbedit -x -u USERNAME

-   修改samba用户登录密码

        smbpasswd USERNAME

-   重启samba

    -   system-v4

            service smbd restart

    -   systemd

            systemctl restart smb

-   查看samba版本

        smbstatus
