---
title: curl
tags: [curl]
date: 2015-09-10 16:55:23
---

-   发送jsonrpc

        curl -X POST -H "Content-Type: application/json" -d '{"method":"HelloService.Say","params":[{"Who":"Test"}], "id":"54321", "jsonrpc": "2.0"}' http://:6061/rpc
