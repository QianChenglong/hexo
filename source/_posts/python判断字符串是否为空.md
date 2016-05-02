---
title: python判断字符串是否为空
categories: [python]
tags: [python, string, empty]
date: 2014-12-05 14:58:43
---

## 代码

-   变量为字符串类型(优雅的方式)

```python
if not string:
    print('not empty')
else:
    print('empty')
```

-   变量类型不确定

```python
if string == '':
    print('not empty')
else:
    print('empty')
```

## 参考

1.  <https://docs.python.org/2/library/stdtypes.html#truth-value-testing>
2.  <http://stackoverflow.com/questions/9573244/most-elegant-way-to-check-if-the-string-is-empty-in-python>
