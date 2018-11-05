## 复合数据类型指针、空指针


1. Go的空指针

+ 当一个指针被定义后没有分配到任何变量时，它的值为nil。

+ nil指针也称为空指针

+ nil在概念上和其他语言的null、None、Null一样，都指代零值或空值

+ 一个指针变量通常缩写为ptr。

2. 空指针的判断：

+ ` if (ptr != nil)`====>ptr 不是空指针

+ `if (ptr == nil)` ====>ptr 是空指针


```go
package main

import (
	"fmt"
)

func main() {
	var ptr *int

	fmt.Printf("ptr类型为%T，值为%v \n", ptr, ptr)

	if ptr == nil {
		fmt.Println("空指针")
	}else{
		fmt.Println("非空指针")
	}
}

/*
ptr类型为*int，值为<nil> 
空指针
[Finished in 5.6s]
*/
```

## 操作指针改变变量的数值

```go
package main

import "fmt"

func main() {
	a := 10
	b := &a
	fmt.Println("--------------------------")
	fmt.Printf("b的数据类型：%T ,数值：%v \n", b, b)
	fmt.Println("b的地址", b)
	fmt.Println("*b的地址", *b)

	*b++
	fmt.Println("a的地址", a)
	var c *int = &a
	fmt.Println("--------------------------")
	fmt.Printf("c的数据类型：%T ,数值：%v \n", c, c)

}


/*
输出结果：
b的数据类型：*int ,数值：0xc00004a080 
b的地址 0xc00004a080
*b的地址 10
a的地址 11
--------------------------
c的数据类型：*int ,数值：0xc00004a080 
[Finished in 3.9s]
*/
```

[Previous](golang-pointDeclaration.md)

[Next](golang-point-functionparameter.md)

[返回本章目录](golang-intermediate-knowledge.md)