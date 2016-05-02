---
title: cscope-使用
categories: [cscope]
tags: [cscope]
date: 2015-02-13 10:54:37
---

# 配合find使用

-   生成文件列表

        find src lib -type f -name "*.[ch]" -fprint cscope.files

-   生成数据库

        cscope -bqf .cscope.out
