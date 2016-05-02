---
title: makefile-目标all作用
categories: [makefile]
tags: [makefile, all]
date: 2015-01-08 14:29:54
---

make在执行makefile中，若没有显式指定目标，默认执行第一个找到的目标。

而一般情况下，一个项目都会生成多个目标(如多个lib，dll，exe)等，所以
需要`all`这个伪目标来生成多个目标。

