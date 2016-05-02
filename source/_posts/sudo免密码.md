---
title: sudo免密码
categories: [linxu]
tags: [linux, sudo, 密码]
date: 2015-02-03 13:25:36
---

-   编辑配置文件

        sudo visudo

-   最后行添加

        用户名  ALL=(ALL) NOPASSWD: ALL

-   保存退出(即时生效)

        :wq
