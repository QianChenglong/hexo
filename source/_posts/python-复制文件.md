---
title: python-复制文件
categories: [python]
tags: [python, 文件操作]
date: 2014-12-24 10:23:34
---

# 代码

-   `shutil.copy(src, dst)`

    -   `src`，源文件
    -   `dst`，目标可以是文件，也可以是目录，当是目录，则在该目录下新建同名文件或**覆盖**同名文件
    -   只拷贝内容，不拷贝文件**元信息**(创建时间，最后访问时间，修改时间等)

-   `shutil.copy2(src, dst)`

    -   完全拷贝(包括**元信息**)，相当于`shutil.copy(src, dst)`+`shutil.copystat(src, dst)`

# 参考

1.  <https://docs.python.org/2/library/shutil.html#shutil.copystat>
