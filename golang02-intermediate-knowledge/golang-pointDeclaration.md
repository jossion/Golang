## 指针

(一).指针的感念

1. 指针是存储另一个变量的内存地址的变量。

+ 变量是一种使用方便的占位符，变量都指向计算机的内存地址

+ 一个指针变量可以指向任何一个值的内存地址

2. 获取变量的地址

+ Go语言的取地址符 `&`，一个变量前使用`&`，会返回该变量的内存地址。

    ```go
    func main(){
        a:=10
        fmt.Printf("变量的地址:%x\n",&a)
    }

    ```
3. Go语言指针的特点：

+ Go语言指针的最大特点是：指针不能运算；

(二). 声明（Dectaration）

1. 声明指针，*T是指针变量的类型，它指向T类型的值。
    var 指针变量名   *指针类型
    + *号用于指定变量是一个指针

    + `var ip *int   //指向整数的指针`

    + `var fp *float32 //指向浮点型的指针`

2. 如何使用指针？（指针使用流程）

+ 定义指针变量

+ 为指针变量赋值

+ 访问指针变量中指向地址的值

+ 获取指针的值，在指针类型的变量前面加上 * 号，来获取指针指向的内容。获取一个指针意味着访问指针指向的变量的值。 语法是：*a


3. 示例代码：


```go
package main

import "fmt"

func main() {
	//	先定义一个实际变量
	a := 123
	//指针变量
	var ip *int
	//	给指针变量赋值
	ip = &a
	fmt.Printf("a的类型是%T \t，值是%v\t \n",a,a)
	fmt.Printf("&a的类型是%T\t，值是%v \t\n",&a,&a)
	fmt.Printf(" ip的类型是%T\t，值是%v\t \n",ip,ip)
	fmt.Printf(" *ip的类型是%T\t，值是%v\t \n",*ip,*ip)
	fmt.Printf("&ip的类型是%T\t,值是%v \t \n",&ip,&ip)
}

```

4. 示例代码二：
```go
package main

import(
	"fmt"
)

type Student struct {
	name string
	age int
	married bool
	sex int8
}

func main(){
	s1 := Student{"Stever",35,true,1}
	s2 := Student{"Sunny",20,false,0}
	var a *Student = &s1
	var b *Student = &s2

	fmt.Println("\n--------------------")
	fmt.Printf("s1的类型%T， 值为%v \n",s1,s1)
	fmt.Printf("s2的类型%T， 值为%v \n",s2,s2)
	fmt.Println("\n--------------------")
	fmt.Printf("a的类型%T， 值为%v \n",a,a)
	fmt.Printf("b的类型%T， 值为%v \n",b,b)
	fmt.Println("\n--------------------")
	fmt.Printf("*a的类型%T， 值为%v \n",*a,*a)
	fmt.Printf("*b的类型%T， 值为%v \n",*b,*b)

	fmt.Println("\n--------------------")
	fmt.Println(s1.name, s1.age, s1.married, s1.sex)
	fmt.Println(a.name, a.age, a.married, a.sex)

	fmt.Println("\n--------------------")
	fmt.Println((*a).name, (*a).age, (*a).married, (*a).sex)
	fmt.Println(&a.name, &a.age, &a.married, &a.sex)
}

/*
输出结果
--------------------
s1的类型main.Student， 值为{Stever 35 true 1} 
s2的类型main.Student， 值为{Sunny 20 false 0} 

--------------------
a的类型*main.Student， 值为&{Stever 35 true 1} 
b的类型*main.Student， 值为&{Sunny 20 false 0} 

--------------------
*a的类型main.Student， 值为{Stever 35 true 1} 
*b的类型main.Student， 值为{Sunny 20 false 0} 
--------------------
Stever 35 true 1
Stever 35 true 1

--------------------
Stever 35 true 1
0xc000044400 0xc000044410 0xc000044418 0xc000044419
[Finished in 3.9s]
*/
```



(六) 使用指针作为函数的参数

1. 示例代码一（基本数据类型指针作为函数参数）

```go

package main

import "fmt"

func main() {
a := 10
fmt.Println("函数调用前的a的值",a)

b:=&a
change(b)
fmt.Println("函数调用后a的值",a)
}

func change(num *int) {
	*num = 20
}
/*
输出结果：
函数调用前的a的值 10
函数调用后a的值 20
[Finished in 3.9s]
*/
```
2. 示例代码二：数据替换
```go
package main

import "fmt"

func main() {
	//定义两个局部变量
	a, b := 100, 200
	//传统函数返回值方式
	a, b = swap0(a, b)
	fmt.Println("第一次交换swap0")
	fmt.Println(a, b)

	//使用指针的方式
	swap(&a, &b)
	fmt.Println("第er次交换swap")
	fmt.Println(a, b)

}

//数据交换传统写法
func swap0(x, y int) (int, int) {
	return y, x
}

//指针作为参数的写法
func swap(x, y *int) {
	*x, *y = *y, *x
}

/*
输出结果：
第一次交换swap0
200 100
第er次交换swap
100 200
[Finished in 4.0s]

*/
```



[Previous](golang-recursive-function.md)

[Next](golang-point-compusitedatatype.md)

[返回本章目录](golang-intermediate-knowledge.md)