---
title: http-head
tags: [http,head]
date: 2015-11-16 15:54:38
---

# 说明

HEAD方法跟GET方法相同，只不过服务器响应时不会返回消息体。
一个HEAD请求的响应中，HTTP头中包含的元信息应该和一个GET请求的响应消息相同。

一个HEAD请求的响应可被缓存，也就是说，响应中的信息可能用来更新之前缓存的实体。如果当前实体跟缓存实体的阈值不同（可通过Content-Length、Content-MD5、ETag或Last-Modified的变化来表明），那么这个缓存就被视为过期了

# 特点

-   简单,快速,耗用资源少

-   响应可被缓存

# 用途

-   测试超链接的有效性、可用性和最近的修改

-   用来获取资源的**元数据**

# 参考

1.  [wiki-超文本传输协议](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE)
