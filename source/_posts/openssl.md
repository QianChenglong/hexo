---
title: openssl
tags: [openssl]
date: 2016-03-28 11:22:38
---

# 常用命令

-   生成RSA公钥，私钥

        openssl genrsa -out private.pem 1024
        openssl rsa -in private.pem -pubout -out public.pem
