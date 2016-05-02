---
title: go-slice
tags: [go, slice]
date: 2015-11-06 14:17:38
---

#　要点

1.  `slice`是一个数组的封装

    ```go
    type slice struct {
        array unsafe.Pointer
        len   int
        cap   int
    }
    ```

1.  使用`fmt.Printf("%T")`打印显示为`[]type`,跟数组类似,但不包括长度

1.  作为传入参数时

    -   若只是改变`slice`中元素的值,不需要穿引用

    -   若改变了`slice`长度或容量,则需要穿指针或返回新`slice`

1.  用数组初始化`slice`时,`slice`容量等于数组的长度减去切割时的索引


    ```go
    var array [10]int
    slice := array[1:5] // cap = 10 - 1 = 9, len = 5 - 1 = 4(array[1, 2, 3, 4])
    fmt.Printf("%T %v\n", array, array)
    fmt.Printf("%T %v %v %v\n", slice, slice, len(slice), cap(slice))

    [10]int [0 0 0 0 0 0 0 0 0 0]
    []int [0 0 0 0] 4 9
    ```

# 参考

1.  <http://blog.golang.org/slices>
1.  <https://blog.go-zh.org/go-slices-usage-and-internals>
