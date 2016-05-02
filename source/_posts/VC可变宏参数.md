---
title: VC可变宏参数
categories: [VC]
tags: [VC, 宏, 可变参数]
date: 2014-12-15 14:31:09
---

# 代码

```c
#define MACRO(s, ...) printf(s, ##__VA_ARGS__)
```

__注：__

-   `##`防止没有参数

# 参考

1.  <http://msdn.microsoft.com/en-us/library/ms177415.aspx>
