---
title: install
tags: [command, install]
date: 2015-09-09 17:08:25
---

-   -D

    所有的参数都被当作要创建的目录名,用来创建不存在的目录

-   -C, --compare

    比较文件内容,再决定更新

-   -m, --mode=MODE

    指定权限

# 实例

-   安装文件

        install -v --compare -D --mode=755 log.py /data/gpxj_server/yun_tong_xun/bin/log.py
