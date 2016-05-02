---
title: mysql-char-vs-varchar
tags: [mysql, char, varchar]
date: 2016-04-07 16:45:41
---

# 区别

## 占用空间

-   char(M)占用空间固定，M[0,255]个字符，具体占用字节与编码相关

-   varchar(M[0,65535])占用空间不固定，因为首部占用1或2B来记录长度M+1(`M<256`)，占用M+2(`255<M<65536`)

## 关于空格

-   在存储字符串到char中时，会填充空格至相应长度

-   取出char类型值时，若`sql_mode`没有设置`PAD_CHAR_TO_FULL_LENGTH`，则会去除尾部空格

    所以导致插入带空格的字符串，取出时却不带有空格！

-   varchar会存储空格和保留空格，不会转换！


# 参考

1.  <http://dev.mysql.com/doc/refman/5.6/en/char.html>
