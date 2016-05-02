---
title: libuser
tags: [libuser]
date: 2016-03-31 17:27:39
---

用户，组信息管理工具

-   /usr/bin/lchfn
-   /usr/bin/lchsh
-   /usr/sbin/lchage
-   /usr/sbin/lgroupadd
-   /usr/sbin/lgroupdel
-   /usr/sbin/lgroupmod
-   /usr/sbin/lid

    查看用户组信息，组成员信息

-   /usr/sbin/lnewusers
-   /usr/sbin/lpasswd
-   /usr/sbin/luseradd
-   /usr/sbin/luserdel
-   /usr/sbin/lusermod

# 实例

1.  添加用户到组

        lgroupmod -M wallace -- vboxsf
