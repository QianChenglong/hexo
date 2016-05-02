---
title: python-字符串和字典转换
categories: [python]
tags: [python, string, dictionary]
date: 2014-12-05 11:20:59
---

## 字典 => 字符串

```python
dict1 = {'one':1, 'two':2, 'three': {'three.1': 3.1, 'three.2': 3.2 }}
str1 = str(dict1)
print(str1)
```

## 字符串 => 字典

```python
dict1 = {'one':1, 'two':2, 'three': {'three.1': 3.1, 'three.2': 3.2 }}
str1 = str(dict1)

dict2 = eval(str1)
print(dict2)
```

## 参考

1.  <http://stackoverflow.com/questions/4547274/convert-a-python-dict-to-a-string-and-back>
