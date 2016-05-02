---
title: python-获取相对路径
categories: [python]
tags: [python, 相对路径]
date: 2014-12-24 10:42:52
---

# 代码

```python
import os

# 获取指定目录相对于当前工作目录的相对路径
print(os.path.relpath('E:/Work/Project/WifiClient/branches/br_WiFi_v0.0.0_r5/httpd/cgi-bin'))
```

# 参考

1.  <http://stackoverflow.com/questions/17506552/python-os-path-relpath-behavior>
1.  <https://docs.python.org/2/library/os.path.html#os.path.relpath>
