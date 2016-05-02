---
title: ubuntu-自动登录
categories: [ubuntu]
tags: [ubuntu, 自动登录]
date: 2015-02-02 14:50:35
---

# UI方式

-   【system setting】 => 【user accounts】

    ![](/img/ubuntu-自动登录-01.png)

# 配置文件

-   打开

        sudo gedit /etc/lightdm/lightdm.conf

-   添加

        autologin-user=username

# 参考

1. <https://wiki.ubuntu.com/LightDM>
