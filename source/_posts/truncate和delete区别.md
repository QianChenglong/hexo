---
title: truncate和delete区别
categories: [database]
tags: [database, sql, truncate, delete]
date: 2015-07-09 14:16:14
---

1.  truncate属于DDL，delete输入DML

1.  truncate不可回滚，delete可回滚

1.  delete可接where子句

1.  truncate执行更快

1.  truncate回收表空间，占用系统日志资源更少

1.  truncate不触发delete触发器

1.  truncate不能被授权
