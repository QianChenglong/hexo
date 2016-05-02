---
title: mysql-安装
categories: [mysql]
tags: [mysql]
date: 2015-06-15 13:29:35
---

# ubuntu(ubuntu-14.04, mysql-5.5)

-   [删除原有]

    sudo apt-get remove --purge mysql-server-5.5 mysql-client-5.5
    sudo apt-get purge mysql-common
    sudo apt-get autoremove
    sudo apt-get clean

-   安装

        apt-get install mysql-server-5.5 mysql-client-5.5

# centos

    sudo yum install mariadb-server

    sudo systemctl start mariadb

# 常见错误

1.  `mysql ERROR: 1050  Table 'plugin' already exists`

    没有卸载干净，执行上面清理命令

    参考：
        1.  <http://askubuntu.com/questions/86939/error-while-installing-mysql-server-5-1>
