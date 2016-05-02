---
title: strcpy和memcpy比较
tags: [c, strcpy, memcpy]
date: 2016-02-21 18:03:27
---

# 不同点

- strcpy是复制源字符串，直到NUL为止（包括NUL)，而memcpy是复制指定个数的字节内容
  ，不会复制到NUL就结束！

# 结论

- 在字符串的复制方面，更推荐使用strcpy，前提是确保dst足够大！
