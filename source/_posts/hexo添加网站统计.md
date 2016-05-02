---
title: hexo添加网站统计
categories: [hexo]
tags: [hexo, 网站统计]
date: 2014-12-12 08:56:02
---

# 环境

-   hexo-theme-chenall

# 百度统计

-   [注册](http://tongji.baidu.com/)

-   获取代码

```js
<script type="text/javascript">
var _bdhmProtocol = (("https:" == document.location.protocol) ? " https://" : " http://");
document.write(unescape("%3Cscript src='" + _bdhmProtocol + "hm.baidu.com/h.js%3F9d0320e39bf03e6be5dc92bf235c8869' type='text/javascript'%3E%3C/script%3E"));
</script>
```

-   修改`hexo-theme-chenall\layout\_analytics\baidu.ejs`

```js
<script type="text/javascript">
var _bdhmProtocol = (("https:" == document.location.protocol) ? " https://" : " http://");
document.write(unescape("%3Cscript src='" + _bdhmProtocol + "hm.baidu.com/h.js%3F9d0320e39bf03e6be5dc92bf235c8869' type='text/javascript'%3E%3C/script%3E"));
</script>
```
