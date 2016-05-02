---
title: autohotkey-字符串
categories: [autohotkey]
tags: [autohotkey, 字符串]
date: 2015-01-16 16:55:37
---

# 字符串是否为空

```autohotkey
if (var = "")
{

}
```

# 字符串拼接

-   表达式方法

```autohotkey
Var := "The color is " . FoundColor
```

-   传统方法

```autohotkey
Var = The color is %FoundColor%
```

参考：

1.  <http://www.autohotkey.com/docs/Variables.htm#Operators>
