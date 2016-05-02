---
title: mysql-datetime
tags: [mysql, datetime]
date: 2015-10-20 16:47:56
---

# 要点

1.  mysql中有`DATE, TIME, DATETIME, TIMESTAMP, YEAR`5种时间类型

1.  时间类型的零值`0000-00-00 00:00:00`

1.  mysql输出时间值时,默认为标准格式`2006-01-02 15:04:05`

1.  mysql读入时间值时(赋值, 比较等操作),会尝试转换各种值如`整数20151020`, `"2015-10-20"`等([详见](https://dev.mysql.com/doc/refman/5.5/en/date-and-time-literals.html))

# 常用函数

1.  格式化时间值

        select date_format('2015-10-20 16:00:04', "%Y%m");

# 参考

1.  <https://dev.mysql.com/doc/refman/5.5/en/date-and-time-functions.html>
1.  <https://dev.mysql.com/doc/refman/5.5/en/date-and-time-types.html>
1.  <https://dev.mysql.com/doc/refman/5.5/en/date-and-time-literals.html>
1.  <https://dev.mysql.com/doc/refman/5.5/en/storage-requirements.html>
