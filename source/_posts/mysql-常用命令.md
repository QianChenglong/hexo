---
title: mysql-常用命令
categories: [mysql]
tags: [mysql]
date: 2015-05-20 13:19:54
---


-   连接数据库

        mysql -h <host> -u <username> -p <password>

-   查看有哪些数据库

        show databases;

-   使用某个数据库

        use <database_name>;

-   查看有哪些表

        show tables;

-   查看系统变量

        show variables;

-   查看表创建语句

        show create table <tablename>;

-   修改root密码

    -   先登录

            SET PASSWORD FOR 'root'@'localhost' = PASSWORD('MyNewPass');
