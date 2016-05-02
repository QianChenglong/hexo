---
title: mysql-数据库备份恢复
tags: [mysql, 备份]
date: 2015-09-28 14:37:30
---

# 备份恢复指定表

    mysqldump -uwallace -pwallace stock_app t_banner_100 >stock_app.t_banner_100

    mysql -uroot -pxianji -hsz003-db -P3309 stock_app <stock_app.t_banner_100
