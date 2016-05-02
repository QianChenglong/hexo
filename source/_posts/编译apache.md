---
title: 编译apache
categories: [apache]
tags: [apache]
date: 2015-07-11 13:36:46
---

# 依赖

-   pcre

-   apr

-   apr-util

# 步骤

## 编译安装pcre

    wget http://sourceforge.net/projects/pcre/files/pcre/8.37/pcre-8.37.tar.bz2
    tar xvf pcre-8.37.tar.bz2
    cd pcre-8.37
    ./configure --prefix=/opt/pcre-8.37
    make
    make install

## 编译安装apache

    wget http://mirrors.hust.edu.cn/apache//httpd/httpd-2.4.12.tar.bz2
    wget http://apache.fayea.com//apr/apr-1.5.2.tar.bz2
    wget http://apache.fayea.com//apr/apr-util-1.5.4.tar.bz2
    tar xvf httpd-2.4.12.tar.bz2
    tar xvf apr-1.5.2.tar.bz2 -C httpd-2.4.12/srclib
    tar xvf apr-util-1.5.4.tar.bz2 -C httpd-2.4.12/srclib
    mv httpd-2.4.12/srclib/apr-1.5.2 httpd-2.4.12/srclib/apr
    mv httpd-2.4.12/srclib/apr-util-1.5.4 httpd-2.4.12/srclib/apr-util
    cd httpd-2.4.12
    ./configure --prefix=/opt/httpd-2.4.12 --with-pcre=/opt/pcre-8.37
    make
    make install

参考：

1.  <http://httpd.apache.org/docs/2.4/install.html>

## 编译安装mod_fcgid([官网](http://httpd.apache.org/download.cgi#mod_fcgid))

    wget http://mirrors.cnnic.cn/apache/httpd/mod_fcgid/mod_fcgid-2.3.9.tar.bz2
    tar xvf mod_fcgid-2.3.9.tar.bz2
    cd mod_fcgid-2.3.9
    APXS=/opt/httpd-2.4.12/bin/apxs ./configure.apxs
    make
    make install

参考：

1. README-FCGID

## 编译安装mod_wsgi([官网](https://code.google.com/p/modwsgi/))

    git clone https://github.com/GrahamDumpleton/mod_wsgi.git
    cd mod_wsgi/
    ./configure --with-apxs=/opt/httpd-2.4.12/bin/apxs --with-python=/usr/bin/python3
    make
    make install
