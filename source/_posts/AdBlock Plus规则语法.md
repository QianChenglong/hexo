---
title: AdBlock Plus规则语法
categories: [AdBlock Plus]
tags: [AdBlock Plus]
date: 2015-04-02 09:28:15
---

-   规则

        正则表达式

-   定义例外规则

        @@|规则

# 元素隐藏

不支持通配符，可在前面加上域名以达到只在某域名下工作

-   根据标签类名

        ##div.textad

-   根据标签ID

        ##div#sponsorad

-   根据标签名

        ##textad

# 属性选择符

通过标签的属性来选择标签以屏蔽，例如`##table[width="80%"]`

可使用正则来匹配属性名

# 参考

1.  <https://adblockplus.org/zh_CN/filters>
