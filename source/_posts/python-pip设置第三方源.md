---
title: python-pip设置第三方源
categories: [python]
tags: [python, pip]
date: 2015-04-01 14:00:09
---

# 命令行指定

pip install -i http://pypi.douban.com/simple/ --trusted-host pypi.douban.com gevent

# 配置文件指定

-   win7

    ~/pip/pip.ini

    ```ini
    [global]
    index-url = http://pypi.douban.com/simple
    [install]
    trusted-host=pypi.douban.com
    ```

-   linux

    vi ~/.pip/pip.conf

    ```ini
    [global]
    index-url = http://pypi.douban.com/simple
    [install]
    trusted-host=pypi.douban.com
    ```


# 第三方源列表

-   http://pypi.douban.com/  豆瓣
-   http://pypi.hustunique.com/  华中理工大学
-   http://pypi.sdutlinux.org/  山东理工大学
-   http://pypi.mirrors.ustc.edu.cn/  中国科学技术大学
