## FOR 循环语句

### （一）概述

1. 在不少实际问题中有许多具有规律行的重复操作，因此需要重复执行某些语句。循环语句包括训话处理语句及训话控制语句

2. 循环处理语句有：  
   |循环类型|描述|
   |:---|:---|
   |`for` 循环|重复执行的代码块|
   |循环嵌套|在 `for` 循环中嵌套一个或多个 `for` 循环|
   | 

3. 循环控制语句可以控制循环体内语句的执行过程。循环控制语句有：
    |控制语句|描述|
    |:---|:---|
    |`break` 语句|经常用于中断当前 `for` 循环或跳出 `switch` 语句|
    |`continue` 语句|跳过当前循环的剩余语句，然后进行下一次循环|
    |`goto` 语句|将控制转义到被标记的语句|
    |
   
### （二）`for` 循环语句

+ 循环语句表示条件满足，可以反复执行的某段代码；

+ `for`是Go语言中唯一的循环语句；

+ 按语法结构来分，GO语言的 `for` 循环有4种形式，只有其中第一种使用分号；

+ `for` 循环中 `for` 关键字后不能加小括号

一. 语法形式：

1. 语法结构：

    ```
    for 吃屎语句inti;条件表达式；结束语句post {
        //循环体代码
    }
    ```
    + 三个组成部分，即：初始化、条件表达式和post都是可选的；

    + 因此这种基本的 `for`新欢语法结构又能演化出四种略有不同的写法。

2.  示例代码：

    ```go
    for i := 0 ; i <= 10 ; i++ {
        fmt.Printf("%d",i)
    }
    ```

3. 语法解释：

    (1). 初始语句init：
    + 初始语句实在第一次循环前执行的语句，一般为赋值表达式，给**控制变量**赋初始值；

    + 如果控制变量在此处被声明，其作用域江北局限在这个 `for` 循环的范围内；在 `for` 循环中生命的变量仅在循环范围内可用；

    + 初始语句可以省略不谢，但是初始预计之后的  `;` 号必须要写；

    ```go
    i := 0
    for ; i<=10;i++{
        fmt.Printf("%d",i)
    }
    ```

    (2). 条件表达式condition:

    + 条件表达式是控制循环与否的开关；

    + 如果表达式为true，则循环继续，否则结束循环；

    + 条件表达式可以省略不写，之后的分号必须要写；

    + 省略条件表达式默认形成无限循环。

    ```go
    i := 0
    for ;;i++{
        if(i>20){
            break
        }
    }
    ```

    (3). 结束语句 Post

    + 一般为赋值表达式，给控制变量递增或递减；

    + post语句将在循环的每次成功迭代之后执行

4. `for` 语句执行过程如下：

    + 先执行初始化语句，对控制变量赋初始值，初始化语句只执行一次；

    + 其次根据控制变量判断条件表达式的返回值，若其值为 `true`满足循环条件，则执行循环体内语句，之后执行post语句，开始下一次循环；
    
    + 执行post语句之后，将重新计算条件表达式的返回值，如果是`true`, 循环继续执行，否则循环终止；然后执行循环体外语句；


二. 语法形式二（for关键字后只有一个条件表达式）

1. 语法结构

+ for循环条件condition{}

+ 效果类似其他编程语言中的while循环

2. 示例代码：

    ```go
    var int
    for i<=10 {
        fmt.Println(i)
        i++
    }
    ```

三. 语法形式三（for关键字后无表达式）

1. 语法结构：
    
    + for{}

    + 效果与其他编程语言的for（；；）{}一致，测试for执行无线循环

2. 示例代码

```go
var i int
for {
    if(i>10){
        break
    }
    fmt.Println(i)
}
```

四. 语法形式四（for ...range）

1. for循环的range格式

    + 对字符串、slice、数组、map等进行迭代循环

2. 语法结构：

    ```go
    for key,value:=range oldMap{
        newMap[key]=value
    }
    ```
3. 案例：遍历字符串，获得字符

```go
//For 关键字后没有 条件表达式

func TraverseString()  {
	str:="username=Liujihe"
	for i,value:=range str  {
	fmt.Printf("第%d位的字符值是：%v,字符是%c \n",i,value,value)
	}
}

```

### 本章节代码：
```go

package main

import "fmt"

func main()  {
	//baseFor()
	//baseFor1()
	//baseFor2()
	//baseFor3()
	//TraverseString()

}
//基本形态
func baseFor()  {
	fmt.Println("\n-----------------------")
	for i:=0;i<10 ;i++  {
		fmt.Printf("%d ",i)

	}
	fmt.Println("\n------------------------")
}

func baseFor1()  {
	fmt.Println("\n------------------------")
	i:=0
	for ;i<10 ;i++  {
		fmt.Printf("%d ",i)

	}
	fmt.Println("\n------------------------")
}
func baseFor2()  {
	fmt.Println("\n-------------------------")
	i:=0
	for ; ;i++  {
		if i>=10{
			break
		}
		fmt.Printf("%d ",i)
	}
	fmt.Println("\n-------------------------")
}
func baseFor3()  {
	fmt.Println("\n-------------------------")
	i:=0

	for ; ; {
		if i>=10{
			break
		}
		i++
		fmt.Printf("%d ",i)
	}
	fmt.Println("\n-------------------------")
}

//For 关键字后没有 条件表达式

func TraverseString()  {
	str:="username=Liujihe"
	for i,value:=range str  {
	fmt.Printf("第%d位的字符值是：%v,字符是%c \n",i,value,value)
	}
}

// For遍历slice
func traverseSlice(){
    arr:=[]int{100,200,300}
    for i,value:=range arr {
        fmt.Println(i ,":",value)
    }
}
```
## 案例：

[返回目录](../golang-controller.md) 

[Next](golang-controller-fornest.md)