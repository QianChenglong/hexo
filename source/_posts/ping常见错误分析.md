---
title: ping常见错误分析
categories: [ping]
tags: [ping, windows, linux, 错误]
date: 2015-02-09 15:54:25
---

# 局域网内，目标不存在或未应答

## 分析

该数据包未发送，因为在tcp/ip在填充目的MAC，执行ARP请求时，没有得到应答，无法确定目的MAC。

## 表象

-   windows

        无法访问目标主机

-   linux

        Destination Host Unreachable

#   非局域网，目标不存在或未应答

## 分析

    该数据包已发送，由下一跳路由负责转发，而对应的机器不存在或未应答

## 表象

-   windows

        请求超时

-   linux

        -   无输出

# 域名解析失败

## 表象

-   windows

        Ping 请求找不到主机 a。请检查该名称，然后重试。

-   linux

        Ping 请求找不到主机 a。请检查该名称，然后重试。
