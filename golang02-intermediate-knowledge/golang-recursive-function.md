## 递归函数

1. 在函数内部，可以调用其他函数。如果一个函数在内部调用自身，这个函数就是递归函数

+ 递归函数必须满足以下两个条件：

    1). 在每一次调用自己是，必须是更接近于解，

    2). 必须有一个终止处理或计算的准则

2. 案例代码：

+ 计算阶乘n! = 1x2x3x.....x n.用函数fact（n）表示，可以看出：fact（n）=n！= 1x2x3x....x(n-1)xn=(n-1)!xn=fact(n-1)xn.所以，fact（n）可以表示n x fact（n-1），只有 n=1时需要特殊处理。

```go
package main

import "fmt"

func main() {
	fmt.Println(factorial(10))
}
func factorial(n int) int {
	if n==0{
		return 1
	}
	return n*factorial(n-1)
}
```
3. 使用递归的注意事项
+ 递归的计算过程

===> factoria(5)

===> 5*fatoria(4)

===> 5* fatoria(4* fatoria(3))

===> 5* fatoria(4* fatoria(3 * fatoria(2)))

===> 5* fatoria(4* fatoria(3 * fatoria(2 * fatoria(1))))

===> 5* (4* (3 * (2 * 1)))

===> 5* (4* (3 * 2 ))

===> 5* (4* 6)

===> 5* (24)

===> 120

+ 递归函数的优点是定义简单，逻辑清晰。理论上，所有的递归函数都可以用循环的方式实现，但循环的逻辑不如递归清晰。

+ 使用递归函数需要注意防止栈的溢出，在计算机中，函数调用时通过栈（stack）这种数据结构实现的，每当进入一个函数调用，栈就会加一层栈，每当函数返回，栈就会减一层。由于栈的大小不是无限的，所以，递归调用的次数过多，会导致栈的溢出。

+ 使用递归函数的有点是逻辑简单清晰，缺点是过深的调用会导致栈的溢出

[Previous](golang-variable-parameter-function.md)

[Next](goang-pointDeclaration.md)

[返回本章目录](golang-intermediate-knowledge.md)
