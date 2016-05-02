---
title: go-string
tags: [go, string, rune, byte]
date: 2015-11-02 18:30:05
---

# 要点

-   a string is in effect a read-only slice of bytes

-   `string`可以存储任意的`bytes`

-   字符串字面值是`utf-8`编码的,所以赋给`string`时,`string`存储的也是`utf-8`编码序列

-   `使用range`得到的是字符(`rune`)序列

    ```go
    for _, b := range str {
        fmt.Printf("%T,%v\n", b, b)
    }
    ```

-   使用`for`迭代,来访问`utf-8`字节(`byte`)

    ```go
    for i := 0; i < len(str); i++ {
        fmt.Printf("%v:%T, %v\n", i, str[i], str[i])
    }
    ```

-   `rune`的意思的`code point`(unicode码元), 底层类型为`int32`

# 参考

1.  <https://blog.golang.org/strings>
1.  <http://golanghome.com/post/207>

