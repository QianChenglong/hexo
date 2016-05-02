---
title: python调试手段
categories: [python]
tags: [python, debug]
date: 2014-12-04 09:18:25
---

## 发生异常时，自动打开`IPython`

-   `crash_on_ipy.py`

```python
import sys


class ExceptionHook:
    instance = None

    def __call__(self, *args, **kwargs):
        if self.instance is None:
            from IPython.core import ultratb
            self.instance = ultratb.FormattedTB(mode='Plain',
                                                color_scheme='Linux', call_pdb=1)
        return self.instance(*args, **kwargs)

sys.excepthook = ExceptionHook()
```

-   将`crash_on_ipy.py`放到项目中，在需要使用该功能的地方`import crash_on_ipy`

## 参考

1.  <http://www.zhihu.com/question/21572891>
