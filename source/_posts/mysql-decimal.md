---
title: mysql-decimal
tags: [mysql, decimal]
date: 2015-10-09 10:42:12
---

# 要点

1.  `decimal`是使用字符存储数字的,所以不存在精度丢失问题

1.  `decimal(M, N)`

    -   M说明存储数位长度(包括小数部分, 又叫精度, precision),取值范围1~65

    -   N说明小数位数(scale, 标度),取值范围0~30,必须不大于M

# 参考

1.  <https://dev.mysql.com/doc/refman/5.1/en/precision-math-decimal-characteristics.html>
1.  <http://stackoverflow.com/questions/2377174/how-do-i-interpret-precision-and-scale-of-a-number-in-a-database>
