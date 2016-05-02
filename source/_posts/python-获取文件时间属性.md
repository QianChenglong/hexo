---
title: python-获取文件时间属性
categories: [python]
tags: [python, 文件, 时间]
date: 2015-01-24 10:00:55
---

# os.path

-   修改时间

        os.path.getmtime()


-   访问时间

        os.path.getactime()


-   创建时间

        os.path.getctime()

# os.stat

-   修改时间

        os.stat.st_mtime

-   访问时间

        os.stat.st_atime

-   创建时间

        os.stat.st_ctime


# 参考

1.  <http://stackoverflow.com/questions/237079/how-to-get-file-creation-modification-date-times-in-python>
