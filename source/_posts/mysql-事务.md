---
title: mysql-事务
categories: [mysql]
tags: [mysql, 事务]
date: 2015-07-09 11:06:35
---

-   当连接设置为自动提交时，所有修改语句永久生效，不可回滚！

-   当事务未提交时，数据只对当前连接可见！

-   mysql默认自动提交


        SELECT @@autocommit;

-   设置为手动提交

        SET autocommit=0;

-   手动提交

        commit;

-   回滚

        rollback;

# 参考

1.  <http://zetcode.com/databases/mysqltutorial/transactions/#autocommit>
