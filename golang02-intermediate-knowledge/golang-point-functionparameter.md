## 指针作为函数参数

切片的指针传递给函数

+ 虽然将指针传递给一个切片作为函数的参数，可以实现对该切片中元素的修改，但这并不是实现这一目标的惯用方法。惯用方法是使用切片。

```go
package main

import "fmt"

func main() {
	a := []int{1, 2, 3, 4,}
	fmt.Println("调用函数前",a)
	modify(&a)
	fmt.Println("调用函数后",a)
}

func modify(arr *[]int) {
	(*arr) [0] = 250
}
/*
输出结果：
调用函数前 [1 2 3 4]
调用函数后 [250 2 3 4]
[Finished in 3.7s]
*/
```


[Previous](golang-point-compusitedatatype.md)

[Next]()

[返回本章目录](golang-intermediate-knowledge.md)