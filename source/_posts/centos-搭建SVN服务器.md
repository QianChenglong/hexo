---
title: centos-搭建SVN服务器
categories: [centos]
tags: [centos, svn]
date: 2015-06-06 15:41:22
---

## 安装svn

    yum install svn

## 配置

1.  建立svn目录

        mkdir /data/svn

1.  创建仓库

        svnadmin create /data/svn/xianji-server

1.  进入配置目录

        cd /data/svn/conf

1.  配置权限

        vi authz

        [/]
        admin = rw

1.  配置账号密码(添加admin用户，密码admin)

        vi passwd

        [users]
        admin = admin

1.  svn服务配置

        vi svnserve.conf

        anon-access = read #匿名用户可读
        auth-access = write #授权用户可写
        password-db = passwd #使用哪个文件作为账号文件
        authz-db = authz #使用哪个文件作为权限文件
        realm = /var/svn/test # 认证空间名，版本库所在目录

## 启动SVN版本库

    svnserve -d -r /var/svn

## 访问

    svn checkout svn://127.0.0.1/xianji-server

