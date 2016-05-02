---
title: go-gorilla-rpc
tags: [go, gorilla, rpc, jsonrpc]
date: 2015-10-13 17:39:32
---

# 流程分析

1.  外部接口

```go
s := rpc.NewServer() // 定义一个rpc server

s.RegisterCodec(json2.NewCustomCodec(&rpc.CompressionSelector{}), "application/json")
// 定义一个codec(用来响应请求)
// 为rpc注册(当收到的http,`Content-Type`为`application/json`时,调用该codec响应处理)
```
# 参考

1.  <https://github.com/gorilla/rpc>
1.  <http://www.gorillatoolkit.org/pkg/rpc>
