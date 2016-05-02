---
title: ubuntu-cron设置日志
categories: [ubuntu]
tags: [ubuntu, cron]
date: 2015-06-09 14:04:27
---

1.  修改rsyslog文件，将`/etc/rsyslog.d/50-default.conf` 文件中的`#cron.*`前的#删掉；

2.  重启rsyslog服务

        service rsyslog restart；

3.  重启cron服务

        service cron restart；

4.  查看

        less /var/log/cron.log
