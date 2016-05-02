---
title: mysql-远程连接
categories: [mysql]
tags: [mysql]
date: 2015-06-05 16:58:10
---

# 环境

-   centos7.0.1-64

-   5.5.41-MariaDB MariaDB Server

# 步骤

1.  确保mysql配置文件`/etc/my.cnf`中没有bind本地地址

1.  授权允许用户远程登录

        grant all PRIVILEGES on 数据库名.表名 to 用户名@'IP' identified by '密码';
        flush privileges;

1.  放行mysql端口

        firewall-cmd --permanent --add-port=3306/tcp
        firewall-cmd --reload
