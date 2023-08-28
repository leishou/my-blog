# Kotlin初探

#### 1.初识

```kotlin
fun main(args:Array<String>){
  println("Hellow kotlin")
}
```

fun:函数名

main ：程序入口

args:接受参数名

Array:数组

String:字符串

println:向控制台打印字符串

------



#### 2.变量与输出

```kotlin
fun main(args:Array<String>){
    val name ="魈";
    name ="真君"
    println("名字是"+name)
}
```

##### PS:常见容器类型

Byte 存储值范围 整数-128~127

Short 存储值范围 整数-32768~32767

Int 存储值范围 整数-2147483648~2147483647

Long 存储值范围 整数-9223372036854775807~9223372036854775807

Float 存储值范围 小数,小数点可以精确到6位

Double 存储值范围 小数,小数点可以精确到15-16位

String 存储值范围 字符串,用"'双引号引起来的字符串都可以存

| 类型   | 描述         | 长度 | 示例                |
| ------ | ------------ | ---- | ------------------- |
| Byte   | 字节         | 8位  | var a: Byte = 1     |
| Short  | 短整型       | 16位 | var b: Short = 1    |
| Int    | 整型         | 32位 | var c: Int = 1      |
| Long   | 长整型       | 64位 | var d: Long = 1L    |
| Float  | 浮点型       | 32位 | var e: Float = 1f   |
| Double | 双精度浮点型 | 64位 | var f: Double = 1.0 |

##### 类型判断

```kotlin
fun main(args:Array<String>){

var name="魈“ //自动推断name的类型是字符串类型

name=18.0 //把小数18.0放入name 程序报错

println("名字是:"+name)

}
```

##### 显式类型声明

```kotlin
fun main(args:Array<String>){
var name
}
```

##### 常量和变量

• 变量是一个容器,里面存放的是可读可写的数据.

• 常量是一个容器,里面存放的是只读的数据.

##### 总结

• **var** 声明**变量**

• **val** 声明**常量**

• 不同的数据类型用不同的容器保存

• kotlin会通过类型推断自动推断数据类型

• 我们可以用: 来显式的指定数据类型

------



#### 3.函数入门

Main函数

main函数是kotlin程序的入口函数

println() 函数

• println函数的作用就是打印括号里面内容到控制台

PS:println()输出内容的时候带换行符

##### 函数编写规则

```kotlin
fun 函数名(参数名:参数类型):返回值类型{
函数体
}
```

```kotlin
fun main(arrag:Array<String>):Unit{
//main: 函数名
//arrag: 函数参数名，名字随便起
//Array<String>: 参数类型 字符串数组
//Unit:返回值类型 Unit代表无返回值 可以省略不写
}
```

```kotlin
//无参无返回值
fun myFun1() {
    println("outerFun")
}
 
//无参有返回值
fun myFun2(): String {
    return"innerFun"
}
 
//有参无返回值
fun myFun3(content: String) {
   println(content)
}
 
//有参有返回值
fun myFun4(content: String): String {
    returncontent
}
当然，没有返回值的函数，也可以明确指定返回值类型为Unit。
//无参无返回值
fun myFun1():Unit{
    println("outerFun")
}
 
//有参无返回值
fun myFun3(content: String) :Unit {
    println(content)
}
```

```kotlin
fun (): Unit {
        
    }
    fun (x: Any): Unit {
        
    }
```

默认生成↑

------

#### 4.val和var

##### 如果一个变量只是声明，需要约束变量的具体类型

![image-20210501210430875](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501210430875.png)

##### Kotlin中变量不能重复定义：

![image-20210501210601959](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501210601959.png)

##### 变量声明有多种形式

![image-20210501210854040](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501210854040.png)

##### 变量类型支持自动推断

![image-20210501211014300](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501211014300.png)

##### 不可变类型变量进行二次赋值会提示错误

![image-20210501211152287](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501211152287.png)

##### val变量优先 

------



#### 5.注释和异常

| **注释类型** | **描述**         | **格式** |
| ------------ | ---------------- | -------- |
| **单行**     | 注释一行         | //       |
| **多行**     | 注释多行         | /**/     |
| **文档**     | 对类或者方法说明 | /***/    |

![image-20210501212909672](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501212909672.png)

![image-20210501213423349](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501213423349.png)

```kotlin
import java.io.BufferedReader
import java.io.StringReader
import java.lang.NumberFormatException
//从BufferedReader中读取内容
fun readNumber(reader:BufferedReader){
    val number :Int = try {
        Integer.parseInt(reader.readLine())
    }catch(e:NumberFormatException){
      0
    }
    //打印结果
    println(number)
}
fun main(args:Array<String>)
{
    val reader1 = BufferedReader(StringReader("123"))
    val reader2 = BufferedReader(StringReader("hello kotlin"))
     readNumber(reader1)
    readNumber(reader2)
}
```

![image-20210501214441683](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20210501214441683.png)