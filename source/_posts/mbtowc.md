---
title: mbtowc
categories: [C]
tags: [C, mbtowc]
date: 2015-02-28 17:02:58
---

用来解决ANSI编码和wchar相关字符编码问题

# 功能

因为ANSI并不是一种固定的编码方式，其取决于当前LOCALE。

所以`mbtowc`根据`LC_CTYPE`来决定**源**的编码方式，将其转换为`wchar`。

程序默认启动`LC_ALL`为`C`。

# 使用场景

-   标准IO

    当使用wchar提供的宽字节版的IO操作函数时，内部需要使用mbtowc族函数进行编码转换

# 参考

1.  <http://www.cplusplus.com/reference/cstdlib/mbtowc/>
1.  <http://blog.sina.com.cn/s/blog_4723adba0100hnb4.html>
