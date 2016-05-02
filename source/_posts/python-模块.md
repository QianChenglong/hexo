---
title: python-模块
categories: [python]
tags: [python, 模块]
date: 2015-03-31 14:32:53
---

# 要点

-   一个*.py文件即一个模块

-   主模块，程序的入口模块

-   文件名(不包括路径和拓展名)即模块名，可通过`__name__`得到，主模块名叫`__main__`

-   模块是一种代码组织方式，具有方便开发，测试，维护，复用等优点

-   模块中的符号表是**私有的**，意味着在模块当中的符号不会与其他模块冲突

-   内建方法`dir()`查看模块名字

# 使用

module.py

```python
var = 1

def func():
    print("Hello world")
```

## 无污染方式(优先使用)

-   导入模块

        import moudle

-   访问模块中的符号(变量名，函数名)

        module.var
        module.func

## 污染方式(不推荐使用)

### 部分导入

-   导入

        from module import var

-   使用

        var

### 全部导入(不会导入单下划线`_`开头的符号)

-   导入模块

        from module import *

-   使用

        var
        func

# 模块搜索路径

-   工作目录

-   sys.path(路径字符串列表)中的顺序搜索

# 标准模块(标准库)

-   有些内建到解释器中

-   有些依赖于平台，如win下的`winreg`

# 参考

1.  <https://docs.python.org/2/tutorial/modules.html>
