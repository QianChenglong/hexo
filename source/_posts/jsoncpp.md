---
title: jsoncpp
categories: [C++]
tags: [C++, jsoncpp]
date: 2015-07-01 15:27:28
---

# 主要的类

| 类名         | 作用                                                                                                                                           |
|--------------+------------------------------------------------------------------------------------------------------------------------------------------------|
| Json::Value  | 可以表示里所有的类型                                                                                                                           |
| Json::Reader | 将json文件流或字符串解析到Json::Value, 主要函数有Parse                                                                                         |
| Json::Writer | 与Json::Reader相反，将Json::Value转化成字符串流，注意它的两个子类：Json::FastWriter和Json::StyleWriter，分别输出不带格式的json和带格式的json。 |

# 常用API

-   判断json中是否有指定成员

        bool isMember("id")

-   取指定值，若不存在，则使用默认值

        Value get(ArrayIndex index, const Value &defaultValue)
# 注意

-   下标访问时，若该元素不存在，则返回值为`json::Value::nullValue`

-   `json::Value::nullValue`转换为空字符串`""`(`\X00`)
