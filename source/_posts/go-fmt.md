---
title: go-fmt
tags: [go, fmt]
date: 2015-10-16 14:31:09
---

# 包内特征

-   3种IO函数

    -   输出

        1.  `Print`用默认格式打印值,中间用空格分隔

        1.  `Println`追加换行

        1.  `Printf`自定义格式化

    -   输入

-   IO源

    1.  默认`stdin`, `stdout`

    1.  `S`族(`fmt.Sprint`, `fmt.Sprintln`, `fmt.Sprintf`),`string`

    1.  `F`族(`fmt.Fprint`, `fmt.Fprintln`, `fmt.Fprintf`),`io.Writer`

# 格式化控制

-   %v  默认格式

-   %+v 打印结构体字段名

-   %T  类型

-   %q  转换为字符串字面值,将非打印字符转义(`\xXX`)

-   %q  转换为字符串字面值,将非打印字符转义(`\xXX`),将`utf-8`编码的字符转换为`\uXXYY`

# 参考

1.  <https://golang.org/pkg/fmt/>
