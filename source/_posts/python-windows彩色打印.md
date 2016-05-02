---
title: python-windows彩色打印
categories: [python]
tags: [python, windows, 彩色打印]
date: 2015-01-16 10:08:22
---

# 安装[colorama](https://pypi.python.org/pypi/colorama)

# 代码

```python
from colorama import init, Fore, Back, Style

init()

print(Fore.RED + 'some red text')
print(Fore.GREEN + 'some green text')
print(Fore.RESET)
print(Back.GREEN + 'and with a green background')
print(Style.DIM + 'and in dim text')
print(Fore.RESET + Back.RESET + Style.RESET_ALL)
print('back to normal now')
```
