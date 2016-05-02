---
title: jsoncpp-使用
categories: [jsoncpp]
tags: [jsoncpp, 使用]
date: 2015-01-20 14:30:33
---

# 前提

```cpp
#include <json/json.h>
```

# 生成json数据对象

```cpp
Json::Value send_data;

send_data["msgType"] = 1;

// json对象
send_data["data"]["ipAddress"] = "192.168.1.1";

// json数组
send_data["name"].append("li");
send_data["name"].append("zhang");

```

# json对象转为字符串

## 转为格式化过的字符串

```cpp
std::string str = send_data.toStyledString();
```

## 转为非格式化字符串

```cpp
Json::FastWriter fast_writer;
std::string str = fast_writer.write(send_data);
```

# 读取json数据

```cpp
Json::Value send_data;
send_data["msgType"] = 1;
send_data["msgCode"] = 10000;
send_data["errCode"] = 0;
send_data["data"]["ipAddress"] = "192.168.1.1";
send_data["data"]["macAddress"] = "";

send_data["msgType"].asInt();
send_data["data"]["ipAddress"].asString();
```
