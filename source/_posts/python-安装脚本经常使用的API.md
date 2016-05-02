---
title: python-安装脚本经常使用的API
tags: [python, install]
date: 2015-04-01 14:06:41
---

-   判断当前系统类型

        platform.system() == 'Windows'
        os.name == 'nt'

-   获取安装绝对路径名(不带"..")

        os.path.abspath(r'./setting.ini')

-   获取脚本所在的目录

        os.path.dirname(os.path.realpath(__file__)

-   获取用户配置完全路径名

        os.path.expanduser(r'~/_vimrc')

-   目录不存在则创建(递归创建)

        if not os.path.exists(directory):
            os.makedirs(directory)

        os.makedirs(os.path.dirname(f[1]), exist_ok=True)
