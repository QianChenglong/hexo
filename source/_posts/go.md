---
title: go
tags: [go]
date: 2015-11-18 14:29:53
---

# 语言特性

1.  代码风格统一(命名,缩进)

    -   以首字母大小写区分成员是`public`还是`privite`

    -   强制缩进风格

1.  错误处理方式优雅统一

    -   错误作为最后一个返回值

1.  资源释放方式优雅统一(`defer`)

1.  非侵入式接口

1.  发布,运维方便

1.  包管理机制

    -   革新了项目管理方式,项目结构和构建顺序依赖于目录组织,引用(import)关系

1.  垃圾自动回收

1.  静态类型

1.  反射

    -   常用于对象的序列化(`json`, `xml`, `gob`,...)

1.  函数多返回值,提供多重赋值

    -   优雅地同时返回结果和错误

    -   返回多个结果不用像C/C++那样,定义额外的结构体或多个传出参数

1.  高效并发,方便的同步机制

1.  自带单元测试

1.  自带很多好用的库,如`log`,`encoding/json`,`net/http`,...

1.  强大好用的命令行工具,如`gofmt`,`gocode`,...

1.  方便的枚举常量定义(`iota`)