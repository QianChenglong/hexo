---
title: node.js-异步IO原理
categories: [node.js]
tags: [node.js, 异步, IO]
date: 2015-04-14 17:24:31
---

# 要点

-   实现`libuv`中间层，根据操作系统采用相应实现(win：IO完成端口，*nix：libev/libeio)

# 参考

1.  [深入浅出Node.js（五）：初探Node.js的异步I/O实现](http://www.infoq.com/cn/articles/nodejs-asynchronous-io)
