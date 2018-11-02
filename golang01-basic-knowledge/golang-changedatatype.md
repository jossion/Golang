## 数据类型转换

### （一）数据类型转换的格式

1. T（表达式）

    * 采用数据类型前置加括号的方式进行类型转换。`T`表示要转换的类型；表达式包括变量、数值、函数返回值等。 

    * 类型转换时，需要考虑两种类型之间的关系和范围，是否会发生数值截断。

    * 布尔型无法与其他类型进行转换。

2. float 与 int之间的转换

    * 需要注意float转int时的精度的损失

3. int转string

    * 其实相当于是byte or rune转string；

    * 该int数值是ASCII码的编号或Unicode字符集的编号。转换成string就是根据字符集将对应的编号的字符查找出来；

    * 当该数值超出Unicode编号范围，则转成的字符串显示为乱码；

    * 例如19968转string 就是“ 一 ”。



#### 例程：

```go
package main

func main(){
    chinese := 90
    english :=80.5
    //avg1 := (chinese + english)/2  //此行会报错：参与计算的两个类型不一致

    avg2 := (float64(chinese) + english)/2 //
    /*
        输出结果：85.45
    */
    /*string型不能转成int型；int型转string是可以的 */

}


```
#### 学习总结：
```








```
[返回上一级](./golang-basic-knowledge.md)