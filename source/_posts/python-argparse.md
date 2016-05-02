---
title: python-argparse
categories: [python]
tags: [python, argparse]
date: 2015-04-09 14:17:45
---

# 概念

示例：

    ls -l test

-   位置参数(Positional Arguments)

    位置参数的作用取决于它的位置和程序(如`cp SRC DST`)

    在示例中，`test`为位置参数

-   可选参数(Optional Arguments)，又叫作选项(option)，开关(switch)

    一般都使用`-`和`--`来标识

    在示例中，`l`为可选参数

# 使用`可选参数`

```python
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("--verbosity", help="increase output verbosity")
args = parser.parse_args()
if args.verbosity:
    print "verbosity turned on"
```

# 参考

1.  <https://docs.python.org/2/howto/argparse.html>
