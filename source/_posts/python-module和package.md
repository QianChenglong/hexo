---
title: python-module和package
categories: [python]
tags: [python, module, package]
date: 2015-1-24 11:39:29
---

# 区别

A module is a single file (or files) that are imported under one import and used. e.g.

    import my_module

A package is a collection of modules in directories that give a package hierarchy.

    from my_package.timing.danger.internets import function_of_love
