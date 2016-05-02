---
title: hexo搭建个人博客
date: 2014-09-19
tags: hexo
---

[官网文档](http://hexo.io/docs/index.html)

## 要求

-   Node.js[官网下载](http://nodejs.org/download/)
-   npm[官网下载](http://nodejs.org/dist/npm/)
-   Git[官网下载](http://git-scm.com/)

## 安装hexo

    npm install -g hexo

`-g`表示安装到`nodejs\node_modules\`目录下

## 建立网站

    hexo init <folder>
    cd <folder>
    npm install

## 创建Git仓库(备选项：gitcafe)

## 部署

-   编辑`_config.yml`

        deploy:
          type: github
          repository: https://github.com/zippera/zippera.github.io.git
          branch: master

-   hexo generate

-   hexo deploy


## 导航栏添加”关于”

1.  hexo new page "about"
2.  到source/about/index.md编辑内容。
3.  在themes/light/_config.yml中，添加如下：

        menu:
          关于: /about

## 安装第三方评论系统

去[多说](http://duoshuo.com/)注册，将ID添加到主题配置文件(_config.yml)

    duoshuo_shortname: qianchenglong

## 添加Google Analytics

去[Google Analytics](http://www.google.com/analytics)注册，配置，将ID添加到主题配置文件(_config.yml)

    google_analytics: UA-54976309-1

## Fix

### `warning: LF will be replaced by CRLF`

-   修改git配置文件

        git config --global core.autocrlf false

-   删除`.deploy`和`public`目录

-   重新生成

        hexo g
        hexo d

## 参考资料

1.  <http://zipperary.com/categories/hexo/>
