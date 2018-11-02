## 闭包函数实现计数器案例


```go
package main

import "fmt"

func main() {
	res := Counter()
	fmt.Printf("%T \n", res)
	fmt.Println("Res地址是:\t", res)
	fmt.Println("第一次\t res值是:\t", res())
	fmt.Println("第二次\t res值是:\t", res())
	fmt.Println("第三次\t res值是:\t", res())
	
	fmt.Println("第四次\t res值是:\t", res())
	fmt.Println("第五次\t res值是:\t", res())
    fmt.Println("第六次\t res值是:\t", res())
//  res1 = Counter()
//	fmt.Println("Res地址是:\t", res)
//	fmt.Println("第一次\t res值是:\t", res1())
//	fmt.Println("第二次\t res值是:\t", res1())
//	fmt.Println("第三次\t res值是:\t", res1())
//	fmt.Println("第四次\t res值是:\t", res1())
//	fmt.Println("第五次\t res值是:\t", res1())
//  fmt.Println("第六次\t res值是:\t", res1())
}

//闭包函数，实现计数器功能
func Counter() func() int {
	i := 0
	res := func() int {
		i++
		return i
	}
	fmt.Println("Counter内部：", res)
	return res
}

/*
输出结果：
Counter内部： 0x490250
func() int 
Res地址是:	 0x490250
第一次	 res值是:	 1
第二次	 res值是:	 2
第三次	 res值是:	 3
第四次	 res值是:	 4
第五次	 res值是:	 5
第六次	 res值是:	 6
[Finished in 5.8s]
*/
```

## 闭包的另一种写法

```go
package main

import "fmt"

func main() {
	res := func() func() int {
		i := 0
		return func() int {
			i++
			return i
		}
	}() //（）表示此函数为立即执行函数
	fmt.Println("第一次\t res值是:\t", res())
	fmt.Println("第二次\t res值是:\t", res())
	fmt.Println("第三次\t res值是:\t", res())
}

```

[Previous](golang-closure-difinition&usage.md)

[Next](golang-recursive-function.md)

[返回本章目录](golang-intermediate-knowledge.md)