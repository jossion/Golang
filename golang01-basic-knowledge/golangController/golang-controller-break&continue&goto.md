## 循环控制语句

### 一. break 语句

1. `break` : 跳出循环体，`break`语句用于在结束其正常执行终止for循环，并开始执行循环之后的语句。

2. 示例：

```go
func main(){
    for i:=1;1<=10;i++{
        if i>5{
            break //如果i>5,终止循环
        }
        fmt.Printf("%d",i)
    }
    fmt.Printf("\n line after for loop")
}
```
### 二. continue语句

1. `continue`有点像`break`，但`continue`不是跳出循环，而是跳过当前循环执行下一次循环语句。`for`循环中，执行`continue`语句会触发for增量语句的执行。换句话说，continue语句用于跳过for循环的当前迭代，循环将继续到下一个迭代。

2.示例：

```go
func main(){
    for i:=1;i<=10;i++{
        if i%2==0{
            continue
        }
        fmt.Printf("%d",i)
    }
}
```

### 三. goto语句

1. goto语句可以无条件的转移到郑旭指定的行

2. 通常与条件语句配合使用，可以用来实现条件转移，构成村换，条数循环体等功能。但是，在结构化程序设计中一般不主张使用goto语句，以免造成程序流程的混乱，使得理解和调试程序都产生困难。

3. goto语法格式如下：

```
Label:statement

goto Label
```

本章节的案例代码：

```go 
//Breack and Continue
package main

import (
	"fmt"
)

/*
 */
func main() {
	//breackContinue()
	//eludeFourGoto()
	primeNumber()

}
func breackContinue() {
	fmt.Println("Break,continued的区别")
	fmt.Println("No.1 Break")
	for i := 0; i <= 10; i++ {
		if i == 5 {
			break
		}
		fmt.Printf("%d ", i)
	}
	fmt.Println()
	fmt.Println("No.2 Continue")
	for i := 0; i <= 10; i++ {
		if i == 5 {
			continue
		}
		fmt.Printf("%d ", i)
	}
	//	打印偶数
	fmt.Println()
	fmt.Println("No.3 打印偶数")
	for i := 0; i <= 20; i++ {
		if i%2 != 0 {
			continue
		}
		fmt.Printf("%d ", i)
	}
	//	去除包含4的数字
	fmt.Println()
	fmt.Println("No.4 剔除包含4的数字")
	num := 0
	for num < 50 {
		num++
		if num%10 == 4 || num/10%10 == 4 {
			continue
		}
		fmt.Printf("%d ", num)
	}

}

func eludeFourGoto() {
	//	goto 控制语句
	fmt.Println()
	fmt.Println("No.5 goto 控制语句")
	num := 0
Loop:
	for num < 50 {
		num++
		if num%10 == 4 || num/10%10 == 4 {
			goto Loop
		}
		fmt.Printf("%d ", num)
	}

}

//输出1~100素数 PrimeNumber
func primeNumber() {
	fmt.Println()
	fmt.Println("No.6 goto 控制语句输出1~100素数")
	num := 0
Loop:
	for num < 100 {
		num++
		//	素数：是只能被1和自身整除的数值
		for i := 2; i < num; i++ {
			if num%i == 0 {
				goto Loop
			}
		}
		fmt.Printf("%d\t ", num)
	}
}

```

[返回目录](../golang-controller.md) 

[基础知识已完结，点击进入中级知识内容](../../golang02-intermediate-knowledge/golang-intermediate-knowledge.md)