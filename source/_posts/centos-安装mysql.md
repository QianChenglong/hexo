---
title: centos-安装mysql
categories: [centos]
tags: [centos, mysql]
date: 2015-06-10 10:09:38
---

# 环境

-   centos-7.0.1-64-server

-   5.5.41-MariaDB MariaDB Server

# 步骤

1.  安装

        yum -y install mariadb-server mariadb

1.  启动

        systemctl start mariadb
        systemctl enable mariadb

1.  配置向导

        mysql_secure_installation
