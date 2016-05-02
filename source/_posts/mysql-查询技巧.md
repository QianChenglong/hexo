---
title: mysql-查询技巧
tags: [mysql]
date: 2015-10-21 16:23:50
---

1.  关联查询时,使用`INNER JOIN <table> USING (<column>)`

    -   `select`结果列,去除了关联列,避免了使用`a.column`
