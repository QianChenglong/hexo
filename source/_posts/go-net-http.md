---
title: go-net-http
tags: [go, net, http]
date: 2015-10-21 17:35:32
---

# http的几个数据结构

-   Request

    客户端发起的http请求,包含请求的URL(资源标识),方法,内容,cooike等

-   Response

    服务端发送的响应(HTTP头,辅助说明响应内容)

-   Conn

    客户端跟服务器的连接

-   Handler

    URL的处理逻辑

    ```go
    type Handler interface {
        ServeHTTP(ResponseWriter, *Request)
    }
    ```

# 工作流程

![](../img/go-net-http-01.png)

1.  创建Listen Socket, 监听指定的端口, 等待客户端请求到来

1.  Listen Socket接受客户端的请求, 得到Client Socket, 接下来通过Client Socket与客户端通信

1.  处理客户端的请求, 首先从Client Socket读取HTTP请求的协议头, 如果是POST方法, 还可能要读取客户端提交的数据, 然后交给相应的handler处理请求, handler处理完毕准备好客户端需要的数据, 通过Client Socket写给客户端

# 使用方法

1.  通过`http.HandleFunc(pattern string, handler func(ResponseWriter, *Request))`处理指定请求(根据URL路由)

1.  通过`htpp.ListenAndServe(addr string, handler Handler)`注册处理器

    -   `Handler`实现了`http.ServeHTTP(ResponseWriter, *Request)`接口

    -   该接口根据URL,请求参数等来路由,比如jsonrpc中根据`method`来路由

1.  通过`http.Handle(pattern string, handler Handler)`注册处理器
