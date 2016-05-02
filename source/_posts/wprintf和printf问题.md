---
title: wprintf和printf问题
categories: [C]
tags: [C, wprintf, printf, IO]
date: 2015-02-28 15:40:17
---

# 问题

两个函数若不经过处理，混合使用将导致另一方的输出无法显示。

# 原因

因为每个标准IO流都具有一个**面向**属性(面向单字节，面向宽字节)，不能混合！

# 参考

1.  <http://stackoverflow.com/questions/8681623/printf-and-wprintf-in-single-c-code>
1.  <http://www.gnu.org/savannah-checkouts/gnu/libc/manual/html_node/Streams-and-I18N.html>
1.  <http://pubs.opengroup.org/onlinepubs/009696699/functions/xsh_chap02_05.html>
