---
title: log4cpp
categories: [C++]
tags: [C++, log4cpp, log]
date: 2015-03-26 09:39:24
---

# 简介

一个C++日志库，模仿Log4j(java日志库)

# 优点

-   可拓展的、多种记录日志方式，包括命令行、文件、回滚文件、内存、syslog服务器、
    win事件日志、VS debuger等

-   可动态调整日志优先级

-   可动态加载配置文件

-   内存占用小，不到200KB

-   跨平台

# 原理

log4cpp主要有3大组件：category、appender、layout。

-   layout

    用来控制输出日志消息的格式，每个appender关联一个layout

-   appender

    用来指定输出目的地

-   category

    一个日志工作体，具有日志级别属性，可以拥有多个appender(一条消息可以输出到多个目的地)

    category被组织成一棵树，子category创建时优先级缺省NOTSET，category缺省会继承父category的appender。
    而如果不希望这种appender的继承关系，log4cpp允许使用additivity 标签，为false时新的appender取代category的appender列表。

# 使用流程

1.  实例化一个layout对象，设置格式

1.  实例化一个appender对象，设置layout

1.  实例化一个category，添加appender


# 参考

1.  <http://log4cpp.sourceforge.net/>
1.  [便利的开发工具-log4cpp快速使用指南](http://www.ibm.com/developerworks/cn/linux/l-log4cpp/)
