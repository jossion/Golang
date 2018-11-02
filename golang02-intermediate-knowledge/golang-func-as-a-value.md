## 函数变量（函数作为值传递）

+ 在Go语言中，函数也是一种类型，可以和其他类型一样被保存在变量中。

+ 可以通过`type`来定义一个自定义类型。函数的参数王权相同（包括：参数类型、个数、顺序），函数的返回值相同。

1. 案例代码NO.1：处理字符串，实现大小写交替

```go 
//函数变量
//函数作为值传递
package main

import (
	"fmt"
	"strings"
)
type caseFunc func(string)string

func main() {
	str:="asdfbgkhiruenfovnrfb"
	//函数调用方式
	fmt.Println(processLetter(str))
	//函数作为参数传入
	fmt.Println()
	fmt.Println(StringTocase(str,processLetter))
//	函数作为type自定义类型
	fmt.Println()
	fmt.Println(StringTocase2(str,processLetter))

}
//处理字符串，实现大小写奇偶交替
func processLetter(str string)string{
	fmt.Println("基本的函数调用")
	result:=""
	for i,value:=range  str{
		if i%2==0{
			result+=strings.ToUpper(string(value))
		}else {
			result+=strings.ToLower(string(value))
		}
	}
	return  result
}
//此函数是将上面封装的大小写排列函数作为参数传递给本函数，用这个参数函数处理第一个要被处理的参数
func StringTocase(str string,fixstr func(string)string) string {
	fmt.Println("函数作为参数传递")
	return fixstr(str)
}

//自定义一个数据类型名字随意，类型是上面封装的处理大小写函数，


func StringTocase2(str string,fixstr caseFunc) string  {
	fmt.Println("自定义函数为数据类型作为参数传递")
	return fixstr(str)
}
```

2. 案例二：遍历整数型切片的奇偶数

```go
package main

import "fmt"

/*步骤：
1.定义一个函数的类型
2.实现定义的函数类型
3.作为参数调用
*/
type myFunc func(int) bool

func main() {
	arr := []int{1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 12, 34, 23, 4, 123}
	fmt.Println("slice= ", arr)
	//	获取奇数元素
	odd := Filter(arr, isOdd)
	fmt.Println("奇数元素是：", odd)
	//	获取偶数元素
	even := Filter(arr, isEven)
	fmt.Println("偶数元素是：", even)
}

//判断整形元素是偶数
func isEven(num int) bool {
	if num%2 == 0 {
		return true
	}
	return false
}

//判断整形元素是奇数
func isOdd(num int) bool {
	if num%2 == 0 {
		return false
	}
	return true
}

//根据函数处理切片，实现奇数偶数分组，返回新的切片
func Filter(arr []int, f myFunc) []int {
	var result []int
	for _, value := range arr {
		if f(value) {
			result = append(result, value)
		}
	}
	return result
}

```
[Previous](golang-functionDeclaration-variable-scope.md)

[Next](golang-anonymousfunction&back-to-the-calling.md)

[返回本章目录](golang-intermediate-knowledge.md)