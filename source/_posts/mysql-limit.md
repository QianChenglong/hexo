---
title: mysql-limit
tags: [mysql, limit]
date: 2015-10-21 16:37:05
---

# 说明

`limit [M,]N`

-   `M`:偏移量,第M+1条

-   `N`:数量

# 功能

1.  获取指定数目列

        select * from t_stock_base limit 1;

1.  获取排序结果中的指定序号,指定书目列

        select * from t_stock_base order by stockid limit 1,2;
