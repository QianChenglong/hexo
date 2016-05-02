---
title: python-获取主模块文件名
categories: [python]
tags: [python, 主模块, 文件名]
date: 2015-04-01 16:01:06
---

```python
import __main__
print __main__.__file__
```

**Note:**

-   交互式shell中执行时，`__main__`没有`__file__`属性


# 参考

1.  <http://stackoverflow.com/questions/606561/how-to-get-filename-of-the-main-module-in-python>
