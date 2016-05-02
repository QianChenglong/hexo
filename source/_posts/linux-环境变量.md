---
title: linux-环境变量
tags: [linux, 环境变量]
date: 2015-09-01 09:50:44
---

# 相关配置文件加载顺序

```
/etc/enviroment => /etc/profile => /etc/bash.bashrc => /etc/profile => /etc/profile.d/*.sh
=> ~/.profile(~/.bash_profile, ~/.bash_login) => ~/.bashrc => ~/.bash_aliases => /etc/bash_completion
```

# 说明

-   /etc/enviroment

    在系统一些核心组件加载完成后最先调用,系统级别的公共环境变量


-   /etc/profile

    在login shell时读取, 相当于是应用级的公共环境变量

-   ~/.profile

    在shell被打开时, 次于/etc/profile执行, 相当于是应用级的用户环境变量
