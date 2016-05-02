---
title: go-rpc
tags: [go, rpc]
date: 2015-11-09 17:30:39
---

# 要点

1.  注册一个类型,即提供一个服务(访问该类型相关的方法)

1.  方法的原型约定

    - the method's type is exported.(只有导出的,在`rpc`包中才可访问)
    - the method is exported.(只有导出的,在`rpc`包中才可访问)
    - the method has two arguments, both exported (or builtin) types.(只有导出的或内建类型,在`rpc`包中才可访问)
    - the method's second argument is a pointer.(第二个为返回参数)
    - the method has return type error.(go风格)

# 参考

1.  <https://golang.org/pkg/net/rpc/>
