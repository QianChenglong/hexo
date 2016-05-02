---
title: go-使用gdb调试
tags: [go, gdb]
date: 2015-09-02 11:04:58
---

# 步骤

1.  编译

        go build -gcflags "-N -l" test.go

1.  调试

        gdb test


# 参考

1.  <http://golang.org/doc/gdb>
1.  [mac下用gdb调试Go程序](http://blog.kenshinx.me/blog/go-gdb/)
