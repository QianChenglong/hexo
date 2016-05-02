---
title: django-manage常用命令
categories: [django]
tags: [django]
date: 2015-06-24 19:01:51
---

-   查看某个命令帮助

        ./manage.py help command

-   生成migrate操作

        python manage.py makemigrations

-   执行migrate操作

        ./manage.py migrate

-   生成多个数据库(1次migrate执行一个数据库)

        ./manage.py migrate
        ./manage.py migrate --database=stock_app

-   创建用户

        ./manage.py createsuperuser

-   修改用户密码

        ./manager.py changepasswd USERNAME
