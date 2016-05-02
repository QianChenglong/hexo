---
title: VC-warning-C4819
categories: [VC]
tags: [VC, warning, C4819]
date: 2015-01-21 16:46:51
---

# 描述

warning C4819: 该文件包含不能在当前代码页(936)中表示的字符。请将该文件保存为 Unicode 格式以防止数据丢失

# 原因

-   源文件采用`utf-8`编码，而VC默认识别成`cp936`编码。
