---
title: go-pointer
tags: [go, pointer]
date: 2015-10-28 17:41:18
---

# 要点

-   在访问`filed`时,`pointer to struct`会自动解引用

    ```go
    type person struct {
        name string
    }
    p := &person{"a"}
    p.name // <=> (*p).name
    ```
-   在调用`method`时,`struct`(`reciver`)会自动转换(取地址,解引用)

    ```go
    type Dog struct {
        name string
    }

    func (d Dog) Bite(target string) {
        fmt.Printf("%v bite %v\n", d.name, target)
    }

    func (d *Dog) Drink(target string) {
        fmt.Printf("%v drink %v\n", d.name, target)
    }

    func main() {
        a := Dog{"a"}
        b := &Dog{"b"}
        a.Bite("b")
        b.Bite("a") // <=> (*b).Bite("a")

        a.Drink("water") // <=> (&a).Drink("water")
        b.Drink("beer")  //
    }
    ```

-   `function`参数不会转换

# 参考

1.  <http://stackoverflow.com/questions/20849751/rule-for-go-pointers-references-dereferencing>
