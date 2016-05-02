---
title: mysq-常用语句
categories: [mysql]
tags: [mysql]
date: 2015-06-25 19:11:43
---

-   获取排序中指定序号列

        SELECT stockid, close/10000, pctchg/100, transday FROM stock_app.t_k_line_day WHERE stockid=? ORDER BY transday DESC LIMIT 1,1

-   mysql下使用update set from select

        UPDATE friends INNER JOIN users ON friends.friendid=users.userid 
        SET friends.friendname=users.username

-   判断等于NULL

        is NULL

-   取指定数目数据

        select transday,preclose from t_k_line_day where '601866.SH' = stockid order by transday desc limit 10;

-   修改列名和定义

        alter table t_day_recommand change column proce price selectprice int(11);

-   修改列定义

        alter table t_day_recommand modify column inperiod int(11) DEFAULT NULL AFTER period;

-   添加列

        alter table t_product add column `issue_index` bigint NOT NULL COMMENT '发行点数, 用来计算份数' after issue_time;

-   命令行执行sql

        mysql -e "select * ...."

-   选择最大值，作为某个比较条件！

        select a.period, a.stockid, b.stockname, c.preclose, 
            (select count(userid) as count from t_follow_buy where stockid = a.stockid and status = 1) as followcount, 
            (a.highestprice - a.selectprice) / a.selectprice as maxincrease
            from stock_app.t_day_recommand a, stock_app.t_stock_base b, stock_app.t_realtime_quotation c 
            where a.priority = 0 and a.stockid = b.stockid and a.stockid = c.stockid and a.period = (select max(period) from t_day_recommand)
            ;

-   update select

        UPDATE table1 alias
        SET (column_name,column_name ) = (
        SELECT (column_name, column_name)
        FROM table2
        WHERE column_name = alias.column_name)
        WHERE column_name = VALUE

-   update table by select

        UPDATE table1 dest, (SELECT * FROM table2 where id=x) src 
        SET dest.col1 = src.col1 where dest.id=x ;

-   Insert to table or update if exists

        INSERT INTO table (id, name, age) VALUES(1, "A", 19) ON DUPLICATE KEY UPDATE    
        name=VALUES(name), age=VALUES(age)

    1.  <http://stackoverflow.com/questions/4205181/insert-to-table-or-update-if-exists-mysql>
    1.  <http://dev.mysql.com/doc/refman/5.1/en/insert-on-duplicate.html>

-   查看mysql用户登录

        select host,user from mysql.user;

-   获取最近天的数据

        SELECT *
        FROM t_k_line_minute
        WHERE stockid="000300.SH" AND DATE(transminute) = (select max(date(transminute)) from t_k_line_minute where stockid = '000300.SH')
        ;

-   删除二进制日志

        PURGE BINARY LOGS TO 'mysql-bin.03';
        PURGE BINARY LOGS BEFORE 201506150000;

-   查看warnings

        show warnings;

-   删除原有主键，增加ID主键

        alter table TABLENAME drop primary key;
        alter table TABLENAME add column id bigint unsigned primary key auto_increment;

-   授权

        grant all privileges on nxb.* to 'dbgateway'@'%' identified by 'xianji';

-   insert by select

        insert into banner_2_0_0 select * from t_banner_100;

-   修改数据库属性

        ALTER DATABASE db_aofei_test CHARACTER SET utf8 COLLATE utf8_unicode_ci;

-   设置auto_increment起始值

        ALTER TABLE tbl AUTO_INCREMENT = 100;
