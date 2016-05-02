---
title: go-json
tags: [go, json]
date: 2015-10-13 16:47:19
---

# 要点

-   编码解码是相对于`json`字符串(`utf-8`编码的slice)来讲的

    -   编码=>将`go`数据类型值转换为`json`字符串

    -   解码=>将`json`字符串转换为`go`中数据类型值

# 常用API

-   `Marshal(v interface{}) ([]byte, error)`

    编码

-   `Unmarshal(data []byte, v interface{}) error`

    解码

-   `NewDecoder(r io.Reader) *Decoder` `(dec *Decoder) Decode(v interface{}) error`

    从实现了`io.Reader`接口中的对象读取`json`字符串来解码

# 参考

1.  [build-web-application-with-golang 7.2 JSON处理](https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/07.2.md)
1.  <https://golang.org/pkg/encoding/json/>
1.  <https://godoc.org/github.com/bitly/go-simplejson>
