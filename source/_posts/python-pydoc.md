---
title: python-pydoc
categories: [python]
tags: [python, pydoc]
date: 2015-04-02 14:38:09
---

# 优点

-   不但可以查看系统本身的文档，还可以查看拓展包，当前目录下的源码文档

# 使用方式

## 交互式命令行

在进入命令行之前，自动导入`help()`

```python
from pydoc import help
```

## 使用http服务器方式

默认包含当前路径源码文档

    pydoc.py -p 8000
