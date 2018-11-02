## For嵌套循环语句

+ Go语言允许在循环体内使用循环

1. 语法结构：

```go
 for [condition|(init;condition;increment)|Range] {
     
     for [condition|(init;condition;increment)|Range]{
        statement(s)
    }
    statement(s)
} 
```



以下是案例代码：

```go
package main

import "fmt"

var lines = 9

func main() {
	//矩形
	printRectangle()
	//左下直角三角形
	printRightTriangleLB()
	//左上直角三角形
	printRightTriangleLT()
	//右下直角三角形
	printRightTriangleRB()
	//右上直角三角形
	printRightTriangleRT()
	//等腰三角
	printRqualTriangle()
	//乘法口洁
	CFKJ()
}

//打印矩形
func printRectangle() {
	fmt.Println("\n打印9*9矩形")
	for i := 1; i <= lines; i++ {
		for j := 1; j <= lines; j++ {
			fmt.Print("❤ ")
		}
		fmt.Println()
	}
}

//打印左下直角三角形
func printRightTriangleLB() {
	fmt.Println("\n打印左下直角三角形:")
	for i := 0; i <= lines; i++ {
		for j := 0; j <= i; j++ {
			fmt.Print("❤ ")
		}
		fmt.Println()
	}
}

//打印左上直角三角形
func printRightTriangleLT() {
	fmt.Println("\n打印左上直角三角形:")
	for i := 0; i <= lines; i++ {
		for j := lines; j >= i; j-- {
			fmt.Print("❤ ")
		}
		fmt.Println()
	}
}

//打印右下直角三角形
func printRightTriangleRB() {
	fmt.Println("\n打印右下直角三角形:")
	for i := 1; i <= lines; i++ {
		//打印空格
		for m := lines; m >= i; m-- {
			fmt.Print("   ")
		}
		for j := 1; j <= i; j++ {
			fmt.Print(" ❤")
		}
		fmt.Println()
	}
}

//打印右上直角三角形
func printRightTriangleRT() {
	fmt.Println("\n打印右上直角三角形")
	for i := 1; i <= lines; i++ {
		for m := 1; m <= i; m++ {
			fmt.Print("   ")
		}
		for j := lines; j >= i; j-- {
			fmt.Print(" ❤")
		}
		fmt.Println()
	}

}

//打印等腰三角形
func printRqualTriangle(){
	fmt.Println("打印等腰三角形")
	for i:=1;i<=lines ;i++  {
		//打印空格
		for m:=lines;m>=i ;m--  {
			fmt.Print("  ")
		}
	//	打印三:
		for j:=1;j<=2*i-1 ;j++  {
			fmt.Print("❤")
		}
		fmt.Println()
	}
}
//打印乘法口诀表
func CFKJ(){
	for i:=1;i<=9 ;i++  {
		for j:=1;j<=i ;j++  {
			fmt.Printf("%d*%d=%d ",j,i,i*j)
		}
		fmt.Println()
	}
}
```
[返回目录](../golang-controller.md) 

[Next](golang-controller-break&continue&goto.md)