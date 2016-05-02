---
title: ubuntu-nautilus快捷键打开terminal
categories: [ubuntu]
tags: [ubuntu, nautilus]
date: 2015-01-29 10:15:19
---

# 环境

-   ubuntu-14.04

-   nautilus-3.10.1

# 步骤

-   安装`nautilus-open-terminal`

        sudo apt-get install nautilus-open-terminal

-   退出nautilus

        nautilus -q

-   编辑配置文件

        gvim ~/.config/nautilus/accels

-   反注释掉该行，并添加映射

    (gtk_accel_path "<Actions>/ExtensionsMenuGroup/NautilusOpenTerminal::open_terminal" "F4")

