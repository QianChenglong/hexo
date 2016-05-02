---
title: openwrt-目录组织
categories: [openwrt]
tags: [openwrt, 目录组织]
date: 2015-02-09 13:23:00
---

-   build_dir/  用于存放所有解压后的源码，并在当中编译

    -   host/   宿主环境下的编译工具源码

    -   toolchain-*   交叉C编译器，C标准库，内核，二进制工具等组件源码

    -   target-*    目标系统的软件包源码

-   staging_dir/    用于存放安装已编译，为了进一步编译软件包，或产生固件镜像

    -   host/   最小化的Linux

    -   toolchain-* 最小化的LInux，带有交叉C编译器，用于去编译剩余的固件部分

    -   target.../root-ramips/  最终的固件


# 参考

1.  <http://stackoverflow.com/questions/26030670/openwrt-buildroot-build-dir-and-staging-dir>
