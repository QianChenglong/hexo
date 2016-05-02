---
title: go-make
tags: [go, make]
date: 2015-10-28 16:45:06
---

# 要点

-   专为用来创建`slice`,`map`,`channel`这3中类型

    -   因为这3中类型依赖于底层数据结构存储,所以必须初始化!

-   返回`T`类型,而不是`*T`

# 参考

1.  <https://golang.org/doc/effective_go.html#allocation_make>
