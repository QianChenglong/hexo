---
title: 快速查看python帮助
categories: python
tags: [python, 帮助]
---

## 第一种：命令行使用

    python -m pydoc CONTENT

## 第二种：使用`python`自包装

### 作用

可以在任意路径下执行`pydoc CONTENT`

### 步骤

-   建立脚本文件`pydoc.py`

        #!/usr/bin/env python
        # encoding: utf-8

        import os
        import sys

        if len(sys.argv) != 2:
            print("usage:pydoc.py OBJECT")
            exit(1)

        cmd = 'python -m pydoc ' + sys.argv[1]
        # print(cmd)
        os.system(cmd)

-   复制到`PATH`目录下

    **建议自建目录**(Win:X:/XXX/bin，Linux：/XXX/bin)，添加该目录到`PATH`

    优点：

    1.  容易管理
    2.  重装系统或系统损坏，不丢失，下次复用方便

-   【Windows建议】

修改环境变量`PATHEXT`追加`.py`，这样直接使用`pydoc CONTENT`即可，不用每次都输入'.py'！

