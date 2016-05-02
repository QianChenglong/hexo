---
title: mysql-prepare-update部分更新
tags: [mysql, prepare, update]
date: 2015-10-19 17:02:38
---

# 需求

有的时候`prepare update`只需要部分更新,其他字段保留原来的值,例如
`update set A=?, B=?`,这里只更新A,但是`prepare`语句执行的时候,
必须需要带2个参数.

# 实现方式

`update set A=COALESCE(?, A), B=COALESCE(?, B)`

prepare(NULL, 1) => 则只更新B

prepare(1, NULL) => 则只更新A

# 参考

1.  <https://dev.mysql.com/doc/refman/5.0/en/comparison-operators.html#function_coalesce>
1.  <http://www.perlmonks.org/?node_id=302181>
