---
title: python-使用py2exe打包
categories: [python]
tags: [python, py2exe, 打包]
date: 2014-12-26 16:07:36
---

# 常见问题

## 没有带上自己的包

```python
import sys
sys.path.append(PACKAGE_DIR)

options = {'py2exe': {
    'packages': ['PACKAGE_NAME']
    }}

```
