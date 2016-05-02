---
title: go-内存分配
tags: [go]
date: 2015-10-28 16:17:31
---

# 要点

1.  在go中,变量定义时,存储到stack还是heap上,由编译器确定

    -   若该变量在离开该作用域,仍被其他引用访问到(通过指针),则存储到heap

# 实例

```go
func f() *string {
    var s string = "Hello world"
    return &s
}
func main() {
    r := f()
    fmt.Printf("%T %v %v\n", r, r, *r)
}
```

1.  与C/C++不同,在go中,可以返回函数内定义的变量地址(因为存储到heap中)

# 结论

1.  在go中,不用关心变量存储位置

# 参考

1.  <https://golang.org/doc/faq#stack_or_heap>
1.  <http://stackoverflow.com/questions/10866195/stack-vs-heap-allocation-of-structs-in-go-and-how-they-relate-to-garbage-collec?rq=1>
