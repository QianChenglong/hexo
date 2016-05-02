---
title: python-获取__main__模块文件名
categories: [python]
tags: [python, __main__]
date: 2014-12-23 10:52:00
---

# 情景

`__main__`模块中`import A`，而`A`模块中需要引用`__main__`的文件名

# 方法1

```python
import __main__
print __main__.__file__
```

缺陷：

当使用`py2exe`时，无法使用

# 方法2

```python
import sys
print sys.argv[0]
```

缺陷：

当使用`python`解释器`-c`传参启动时，无效

# 参考

1.  <http://stackoverflow.com/questions/606561/how-to-get-filename-of-the-main-module-in-python>
1.  <http://www.acnenomor.com/4440072p1/how-to-get-filename-of-the-main-module-in-python>
