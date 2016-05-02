---
title: go-package
tags: [go, package]
date: 2015-09-18 16:52:51
---

-   包内的首字母大写为可导出符号,在其他包中使用

-   `_ import *`表示导入该包,但不直接使用该包内的可导出符号(如使用`go-sql-driver/mysql`)

-   导入包时,go会自动执行包内的`init()`
