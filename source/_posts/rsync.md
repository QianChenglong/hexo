---
title: rsync
categories: [rsync]
tags: [rsync]
date: 2015-06-18 11:14:28
---

# 功能

远程同步

# 常用选项

-   使用密码文件认证

        rsync -avzP --password-file=/cygdrive/E/Soft/rsync/bin/cwRsync_5.4.1_x86_Free/rsyncd.scrt  /cygdrive/E/Work/project/gupiaoxianji/xianji-server/data wallace@%SERVER%::dbdata

-    --exclude={.ccache,build}

    排除多个目录

-   --chown=www-data:www-data

    修改文件所有者
