---
title: apache-fastcgi配置
tags: [apache, fastcgi, mod_fcgid]
date: 2015-08-05 14:15:24
---

-   可执行

        Options +ExecCGI

-   该目录下所有文件作为fastcgi程序执行

        SetHandler fcgid-script

-   指定文件拓展名作为fastcgi程序执行

        AddHandler fastcgi-script fcg fcgi fpl
