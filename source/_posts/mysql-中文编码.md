---
title: mysql-中文编码
tags: [mysql, 编码]
date: 2015-11-02 16:41:06
---

# 说明

-   存储使用`UTF-8`(中文占用3B,英文占用1B)

# 要点

-   `char(n)`或`vchar(n)`中`n`指的是字符容量,具体占用字节空间取决于编码集

-   字符

    -   一个汉字即一个字符

    -   一个英文字母即一个字符

-   `char_length`   获取字符串的字符数目

-   `length`    获取字节数(所占空间大小)

# 实验

## 环境

```sql
mysql> show variables like 'character%';
+--------------------------+----------------------------+
| Variable_name            | Value                      |
+--------------------------+----------------------------+
| character_set_client     | utf8                       |
| character_set_connection | utf8                       |
| character_set_database   | utf8                       |
| character_set_filesystem | binary                     |
| character_set_results    | utf8                       |
| character_set_server     | utf8                       |
| character_set_system     | utf8                       |
| character_sets_dir       | /usr/share/mysql/charsets/ |
+--------------------------+----------------------------+
mysql> select char_length('a');
+------------------+
| char_length('a') |
+------------------+
|                1 |
+------------------+
1 row in set (0.00 sec)

mysql> select length('a');
+-------------+
| length('a') |
+-------------+
|           1 |
+-------------+
1 row in set (0.00 sec)

mysql> select char_length('汉');
+--------------------+
| char_length('汉')  |
+--------------------+
|                  1 |
+--------------------+
1 row in set (0.00 sec)

mysql> select length('汉');
+---------------+
| length('汉')  |
+---------------+
|             3 |
+---------------+
1 row in set (0.00 sec)
```

# 参考

1.  <https://dev.mysql.com/doc/refman/5.0/en/string-functions.html>
