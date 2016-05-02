---
title: mysql-alias
tags: [mysql, alias]
date: 2015-10-10 11:32:35
---

# 要点

-   对目标列使用,

    -   输出列名可读性更强

-   对表名使用

    -   简写表名

    -   同名表关联

-   在select的目标输出列中(`select_expr`)

    -   别名可以在`GROUP BY`,`ORDER BY`,`HAVING`中使用

    -   标准SQl不允许在`WHERE`中使用

        因为`WHERE`是执行的,而`SELECT`目标列是基于`WHERE`结果的,
        所以`WHERE`中不能使用还没产生的别名!

-   `AS`可以省略

        select id userid from user;
        select a.id from user a;


# 参考

1.  <https://dev.mysql.com/doc/refman/5.0/en/problems-with-alias.html>
