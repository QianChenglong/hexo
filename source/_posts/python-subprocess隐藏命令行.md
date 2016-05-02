---
title: python-subprocess隐藏命令行
categories: [python]
tags: [python, subprocess]
date: 2014-12-25 13:46:50
---

# 代码

```python
import subprocess
startupinfo = subprocess.STARTUPINFO()
startupinfo.dwFlags = subprocess.CREATE_NEW_CONSOLE | subprocess.STARTF_USESHOWWINDOW
startupinfo.wShowWindow = subprocess.SW_HIDE
subprocess.Popen(["ping", "-c 1", ip], stdout=subprocess.PIPE, stderr=subprocess.PIPE, startupinfo=startupinfo)
```

# 参考

1.  <http://code.activestate.com/recipes/578300-python-subprocess-hide-console-on-windows/>
