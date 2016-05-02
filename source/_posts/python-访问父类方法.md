---
title: python-访问父类方法
categories: [python]
tags: [python, 父类]
date: 2015-04-03 15:07:53
---

```python
class A(object):
    def __init__(self):
        pass

```

# 使用`super`

要求父类必须派生自`object`!

```python
class B(A):
    def __init__(self):
        super(B, self).__init__()
```

# 使用类名访问

```python
class B(A):
    def __init__(self):
        A.__init__(self)
```

# 参考

1.  <http://stackoverflow.com/questions/753640/inheritance-and-overriding-init-in-python>
