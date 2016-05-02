---
title: go-database
tags: [go, database]
date: 2015-09-25 10:42:41
---

# 要点

-   `go`官方没有直接提供数据库驱动,而是定义了一些标准接口(`database/sql`)

-   第三方驱动通过包初始化函数`init()`调用`sql.Register(name string, driver driver.Driver)`完成注册

## 重要类型

## `driver.Conn`

Conn是一个数据库连接的接口定义，他定义了一系列方法，这个Conn只能应用在一个goroutine里面，不能使用在多个goroutine里面

```go
type Conn interface {
    Prepare(query string) (Stmt, error)
    Close() error
    Begin() (Tx, error)
}
```

-   Prepare函数返回与当前连接相关的执行Sql语句的准备状态，可以进行查询、删除等操作。

-   Close函数关闭当前的连接，执行释放连接拥有的资源等清理工作.

-   Begin函数返回一个代表事务处理的Tx，通过它你可以进行查询,更新等操作，或者对事务进行回滚、递交。

## `driver.Stmt`

Stmt是一种准备好的状态，和Conn相关联，而且只能应用于一个goroutine中，不能应用于多个goroutine

```go
type Stmt interface {
    Close() error
    NumInput() int
    Exec(args []Value) (Result, error)
    Query(args []Value) (Rows, error)
}
```

-   Close函数关闭当前的链接状态，但是如果当前正在执行query，query还是有效返回rows数据

-   NumInput函数返回当前预留参数的个数，当返回>=0时数据库驱动就会智能检查调用者的参数。当数据库驱动包不知道预留参数的时候，返回-1

-   Exec函数执行Prepare准备好的sql，传入参数执行update/insert等操作，返回Result数据

-   Query函数执行Prepare准备好的sql，传入需要的参数执行select操作，返回Rows结果集

## `driver.Tx`

事务处理一般就两个过程，递交或者回滚

```go
type Tx interface {
    Commit() error
    Rollback() error
}
```

## `driver.Execer`

这是一个Conn可选择实现的接口

```go
type Execer interface {
    Exec(query string, args []Value) (Result, error)
}
```

如果这个接口没有定义，那么在调用DB.Exec,就会首先调用Prepare返回Stmt，然后执行Stmt的Exec，然后关闭Stmt。

## `driver.Result`

这个是执行Update/Insert等操作返回的结果接口定义

```go
type Result interface {
    LastInsertId() (int64, error)
    RowsAffected() (int64, error)
}
```

-   LastInsertId函数返回由数据库执行插入操作得到的自增ID号。

-   RowsAffected函数返回query操作影响的数据条目数。

## `driver.Rows`

Rows是执行查询返回的结果集接口定义

```go
type Rows interface {
    Columns() []string
    Close() error
    Next(dest []Value) error
}
```

-   Columns函数返回查询数据库表的字段信息，这个返回的slice和sql查询的字段一一对应，而不是返回整个表的所有字段。

-   Close函数用来关闭Rows迭代器。

-   Next函数用来返回下一条数据，把数据赋值给dest。dest里面的元素必须是driver.Value的值除了string，返回的数据里面所有的string都必须要转换成[]byte。如果最后没数据了，Next函数最后返回io.EOF。

## `driver.RowsAffected`

RowsAffected其实就是一个int64的别名，但是他实现了Result接口，用来底层实现Result的表示方式

```go
type RowsAffected int64

func (RowsAffected) LastInsertId() (int64, error)

func (v RowsAffected) RowsAffected() (int64, error)
```

## `driver.Value`

Value其实就是一个空接口，他可以容纳任何的数据

```go
type Value interface{}
```

drive的Value是驱动必须能够操作的Value，Value要么是nil，要么是下面的任意一种

```go
int64
float64
bool
[]byte
string   [*]除了Rows.Next返回的不能是string.
time.Time
```

## `driver.ValueConverter`

ValueConverter接口定义了如何把一个普通的值转化成driver.Value的接口

```go
type ValueConverter interface {
    ConvertValue(v interface{}) (Value, error)
}
```

在开发的数据库驱动包里面实现这个接口的函数在很多地方会使用到，这个ValueConverter有很多好处：

-   转化driver.value到数据库表相应的字段，例如int64的数据如何转化成数据库表uint16字段
-   把数据库查询结果转化成driver.Value值
-   在scan函数里面如何把driver.Value值转化成用户定义的值

## `driver.Valuer`

Valuer接口定义了返回一个driver.Value的方式

```go
type Valuer interface {
    Value() (Value, error)
}
```

很多类型都实现了这个Value方法，用来自身与driver.Value的转化。

# 使用相关

## `sql.Stmt`

`sql.DB.Prepare`返回的语句操作

```go
(s *Stmt) Exec(args ...interface{}) (Result, error) // 带参数执行prepare语句(insert, update...)
(s *Stmt) Query(args ...interface{}) (*Rows, error) // 带参数执行select语句, 返回结果集
(s *Stmt) QueryRow(args ...interface{}) *Row // 带参数执行select语句,通过scan获取单行结果!(函数糖)
(s *Stmt) Close() error // 释放资源
```

## `sql.Row`

`QueryRow返回`,结合`scan`用来获取单行查询结果

# 参考

1.  [go web编程](https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/05.1.md)
