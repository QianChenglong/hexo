---
title: go-struct-tag
tags: [go, struct tag]
date: 2015-09-16 15:56:18
---

# 作用

`struct`中可以附加一个`tag`,用来定制一些行为

如在`encoding/json`中,因为go,默认首字母大写为导出的,而希望编码为json字符串时,
首字母为小写.

```go
type Person struct {
    FirstName    string    `json:"first_name"`
    LastName     string    `json:"last_name"`
    MiddleName   string    `json:"middle_name,omitempty"`
}
```

# 注意

-   附加`omitempty`时,当值为`null`时,不包含该字段

-   附加`string`时,不管原类型,都转换为`json string`

-   附加`json:"-"`,不转换该字段

# 参考

1.  <http://stackoverflow.com/questions/10858787/what-are-the-uses-for-tags-in-go>
1.  <http://golang.org/pkg/reflect/#StructTag>
1.  <https://groups.google.com/forum/#!topic/golang-china/jDyG0r_atxQ>
1.  <https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/07.2.md>
