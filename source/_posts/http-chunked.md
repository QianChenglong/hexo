---
title: http-chunked
tags: [http, chunked]
date: 2015-10-19 17:40:49
---

# 要点

-   在不指定`Content-Length`的情况下,来传输数据,常用来配合`gzip`使用,边压缩边传输

-   用一系列分块来传输。每个分块包含十六进制的长度值和数据，长度值独占一行，长度不包括它结尾的 CRLF（\r\n），
    也不包括分块数据结尾的 CRLF。最后一个分块长度值必须为 0，对应的分块数据没有内容，表示实体结束

# 参考

1.  [wiki-chunked](https://zh.wikipedia.org/wiki/%E5%88%86%E5%9D%97%E4%BC%A0%E8%BE%93%E7%BC%96%E7%A0%81)
