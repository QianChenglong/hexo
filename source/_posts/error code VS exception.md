---
title: error code VS exception
categories: [编程]
tags: [error code, exception, 错误处理]
date: 2015-03-30 11:50:22
---

# 错误代码

## 缺点

-   错误处理麻烦

    函数调用后，需要检查其错误代码，并对相应错误进行处理(错误处理策略复杂)，
    需要写很多"不相干"代码，包含很多`if-else`，代码丑陋，很难周密性检查，需要花很多精力处理。

# 异常
