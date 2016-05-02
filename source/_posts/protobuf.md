---
title: protobuf
tags: [protobuf]
date: 2016-03-18 18:11:37
---

# 优点

-   二进制编码，格式紧凑，编解码快，省流量

# 命令

    protoc [OPTION] PROTO_FILES


# 基本用法

-   输出c++代码

        protoc --cpp_out=. base.proto

# API

-   基本类型(`uint32`、`string`等)提供了`set_`方法

-   singular(`单数`) message字段(自定义消息)，提供`mutalbe_`方法设置值，没有`set_`方法

-   repeated字段

    -   `_size`查询数量
    -   下标访问(获取，修改)
    -   `add_`添加(返回指针来修改数据)

# 编码风格(<https://developers.google.com/protocol-buffers/docs/style>)

-   消息类型

    CamelCase(with an initial capital)

-   字段

    underscore_separated_names

```proto
message SongServerRequest {
  required string song_name = 1;
}

C++:
  const string& song_name() { ... }
  void set_song_name(const string& x) { ... }

Java:
  public String getSongName() { ... }
  public Builder setSongName(String v) { ... }
```

-   枚举

    Use CamelCase (with an initial capital) for enum type names and CAPITALS_WITH_UNDERSCORES for value names

```proto
enum Foo {
  FIRST_VALUE = 1;
  SECOND_VALUE = 2;
}
```

-   service

    CamelCase (with an initial capital) for both the service name and any RPC method names

```proto
service FooService {
  rpc GetSomething(FooRequest) returns (FooResponse);
}
```
