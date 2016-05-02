---
title: go-new
tags: [go, new]
date: 2015-10-27 10:16:09
---

# 要点

-   填充零值(不会进一步初始化),返回指针

-   可用来简化定义内部类型(`int`, `string`...),因为`&int`是非法的

    ```go
    i := new(int)

    var j int
    i = &j
    ```

# 参考

1.  <https://golang.org/doc/effective_go.html#allocation_new>
1.  <http://stackoverflow.com/questions/9320862/go-why-would-i-make-or-new>
1.  <http://stackoverflow.com/questions/13244947/is-there-a-difference-between-new-and-regular-allocation?lq=1>
