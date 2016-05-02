---
title: mysql-主从数据库配置
categories: [mysql]
tags: [mysql]
date: 2015-06-10 09:45:34
---

# 环境

-   ubuntu-14.04

-   mysql-5.5

# 步骤

-   修改主数据库配置

        vi /etc/my.cnf.d/server.cnf

        [mysqld]
        server-id=1
        binlog-do-db=<database-name>
        relay-log=/var/lib/mysql/mysql-relay-bin
        relay-log-index=/var/lib/mysql/mysql-relay-bin.index
        log-error=/var/lib/mysql/mysql.err
        master-info-file=/var/lib/mysql/mysql-master.info
        relay-log-info-file=/var/lib/mysql/mysql-relay-log.info
        log-bin=/var/lib/mysql/mysql-bin

-   重启mysql

        systemctl restart mariadb

-   给从库复制权限

        grant replication slave on *.* to 'slave'@'%' identified by 'slave';

-   锁表，以便备份

        FLUSH TABLES WITH READ LOCK;

-   记录下当前主库日志状态，以便从库同步

         SHOW MASTER STATUS;

-   导出要同步的数据库

        mysqldump -uroot -p --master-data <database-name>;

-   解锁表

        UNLOCK TABLES;

## 从服务器配置

-   修改配置

        vi /etc/my.cnf.d/server.cnf

        [mysqld]
        server-id=2
        replicate-do-db=test2
        relay-log=/var/lib/mysql/mysql-relay-bin
        relay-log-index=/var/lib/mysql/mysql-relay-bin.index
        log-error=/var/lib/mysql/mysql.err
        master-info-file=/var/lib/mysql/mysql-master.info
        relay-log-info-file=/var/lib/mysql/mysql-relay-log.info
        log-bin=/var/lib/mysql/mysql-bin

-   修改权限控制

         vi /etc/apparmor.d/usr.sbin.mysqld

-   连接master

        mysql -uroot -p
        stop slave;
        CHANGE MASTER TO MASTER_HOST='172.18.1.192', MASTER_USER='slave', MASTER_PASSWORD='slave', MASTER_LOG_FILE='mysql-bin.000001', MASTER_LOG_POS=822;
        start slave;
        show slave status\G

# 常见错误

-   `mysql Last_IO_Errno: 1045`

    账号密码认证方面错误。

    可以现在master上尝试登陆，看是否成功。

#   其他常用命令

-   重新设置slave

        RESET SLAVE;

-   查看进程状态

        SHOW PROCESSLIST \G;

# 参考

1.  <https://dev.mysql.com/doc/refman/5.1/en/replication-howto.html>
1.  <https://lesca.me/archives/mysql-master-slave-replication-on-centos-7.html>
