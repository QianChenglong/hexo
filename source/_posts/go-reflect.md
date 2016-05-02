---
title: go-reflect
tags: [go, reflect]
date: 2015-09-18 14:07:45
---

# 要点

-   从根本上说,反射只是一个机制,用来检查存储在接口内的类型和值,
    所以在反射中,有2个类型分别对应(`reflect.Type`, `reflect.Value`),
    分别由`reflect.TypeOf(i interface{}) Type`和`reflect`

# 常用API

## function

-   `Indirect(v Value) Value`

    -   若`v`是`nil pointer`,则返回`zero value`
    -   若`v`是`not nil pointer`,则返回其指向的值
    -   若`v`不是指针,则返回其本身

    有些接口同时支持指针值和非指针值,通过这个帮助函数,可以简化代码
    可参考`goriila/rpc`中,` (m *serviceMap) register(rcvr interface{}, name string)`中,获取`rcvr`的类型名

## `reflect.Value`

-   `(v Value) Elem() Value`

    -   `v`要求是`interface`或`pointer`,其他则`panic`

    -   `interface`则返回其动态类型值

    -   `pointer`则返回指向的值

    -   若`v`是`nil`,则返回零值

# 参考

1.  <http://blog.golang.org/laws-of-reflection>
