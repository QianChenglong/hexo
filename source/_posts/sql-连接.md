---
title: sql-连接
categories: [sql]
tags: [sql, 连接]
date: 2015-06-11 10:09:05
---

# 作用

-   SQL通过**连接**将多个表关联起来,是实现数据组合最重要的一环!

-   所以**连接**的本质是通过一些生成手段来获取目标集合,再通过对**连接**生成的集合(临时表)加以筛选,得到目标数据

# 连接方式

## 内连接(INNER JOIN)

只返回两个表中连接条件成立的行

## 外连接(OUTER JOIN)

外连接并不要求连接的两表的每一条记录在对方表中都一条匹配的记录.

### 全外连接(FULL OUTER JOIN)

保留2边都不匹配的数据

###  左连接(LEFT OUTER JOIN, sql中简写`LEFT JOIN`)

保留左边不匹配的数据

### 右外连接(RIGHT OUTER JOIN)

保留右边不匹配的数据

## 交叉连接(CROSS JOIN)

示例:

```sql
SELECT a.*, b.* FROM A, B WHERE A.id = b.id
```

执行过程:

1.  将A与B做笛卡尔积运算,得到临时表C

1.  再通过过滤条件`A.id = b.id`,得到结果集

## 自连接(SELF JOIN)

一种交叉连接的特例,和自身交叉

# 参考

1.  [widi-连接](https://zh.wikipedia.org/wiki/%E8%BF%9E%E6%8E%A5_(SQL))
1.  <http://www.mysqltutorial.org/mysql-update-join/>
