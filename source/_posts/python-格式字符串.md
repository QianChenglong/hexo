---
title: python-格式字符串
categories: [python]
tags: [python, 字符串]
date: 2014-12-24 16:53:32
---

# 背景

因python不提供隐式类型转换，不支持类似`string + int`等操作，所以字符串的连接
需要使用其他的方法。

# 2.6之后推荐使用`string.format()`

# 基本用法

-   `string`连接其他类型

```python
var = False
'True Or {}!'.format(var)
```

-   命名参数

```python
madlib = " I {verb} the {object} off the {place} ".format(verb="took", object="cheese", place="table")
```

# 不推荐使用`%`

原因，参见[PEP-3101](https://www.python.org/dev/peps/pep-3101/)

# 参考

1.  <https://www.python.org/dev/peps/pep-3101/>
1.  <https://docs.python.org/2.7/library/string.html#formatspec>
1.  <http://youngsterxyf.github.io/2013/01/26/python-string-format/>
1.  <http://www.pythonclub.org/python-basic/print>
