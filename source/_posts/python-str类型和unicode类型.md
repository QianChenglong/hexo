---
title: python-str类型和unicode类型
categories: [python]
tags: [python, str, unicode]
date: 2014-12-08 17:29:23
---

# 概念

str object和unicode object是两种不同的类型

## 字符串

字符组成的序列

而字符是经过编码的，常见的编码如ASCII，GB2312，UTF-8等等

### 词法

引号括起来的字符序列

## unicode字符串

unicode码元序列

在python里，16-bit的unicode，对应的是ucs2编码。32-bit对应的是ucs4编码

通过`sys.maxunicode`可以查看当前Python的unicode编码

### 词法

引号括起来的字符序列，前面加`u`，如`u'Hello world'`

# 参考

1.  <https://docs.python.org/2/library/stdtypes.html#sequence-types-str-unicode-list-tuple-bytearray-buffer-xrange>
1.  <http://blog.csdn.net/ktb2007/article/details/3876429>
