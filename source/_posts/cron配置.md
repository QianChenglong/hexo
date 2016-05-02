---
title: cron配置
categories: [cron]
tags: [cron]
date: 2015-06-09 14:12:49
---

# 环境

-   ubuntu-14-10-64-server

# 配置文件

-   用户配置文件

        /var/spool/cron/root

-   系统全局配置

        /etc/crontab
        /etc/cron.*

# 配置通过SMTP发送邮件

-   先卸载postfix

        apt-get purge postfix
        apt-get purge mailutils
        apt-get auto-remove

-   安装msmtp

        apt-get install msmtp
        apt-get install msmtp-mta

-   编辑配置文件

        defaults
        logfile /var/log/msmtp.log
        syslog on
        aliases /etc/aliases

        account default
        host smtp.exmail.qq.com
        from qiancl@gupiaoxianji.com
        user qiancl@gupiaoxianji.com
        password ******
        auth on
        tls on
        tls_certcheck off

-   测试是否成功

        echo -e "Subject: Test Mail\r\n\r\nThis is a test mail" |msmtp --debug -t qiancl@gupiaoxianji.com

-   让cron使用smtp发送

        crontab -e

        MAILTO=qiancl@gupiaoxianji.com

# 调试

-   每分钟执行，查看执行是否成功

        * * * * * CMD
