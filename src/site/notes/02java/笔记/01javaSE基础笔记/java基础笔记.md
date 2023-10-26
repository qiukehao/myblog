---
{"dg-publish":true,"permalink":"/02java//01java-se/java/","dgPassFrontmatter":true}
---

# java基础
## Java基础知识
### 人机交互
#### 1.1 什么是cmd？
就是在windows操作系统中，利用命令行的方式去操作计算机。
我们可以利用cmd命令去操作计算机，比如：打开文件，打开文件夹，创建文件夹等。
#### 1.2 如何打开CMD窗口？
按下快捷键：win + R。
此时会出现运行窗口。
在运行窗口中输出cmd
输出回车。
解惑：
​	cmd默认操作C盘下的users文件夹下的XXX文件夹。（XXX就是计算机名）

#### 1.3 常用CMD命令
扩展一个小点：
​	在很多资料中都说成是DOS命令，其实是不对的。真正的DOS命令是1981年微软和IBM出品的MS-DOS操作系统中的命令才叫做DOS命令。
​	而在Windows中，win98之前的操作系统是以非图形化的DOS为基础的，可以叫做DOS命令。到了2000年以后，windows逐渐的以图形化界面为主了，这个时候就不能叫DOS命令了，他只是模拟了DOS环境而已，很多的原本的DOS命令已经无法使用了，所以这个时候叫做CMD命令会更准确一些。
常见的CMD命令如下：

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051429242.png)


#### 1.4 cmd练习
需求：
利用cmd命令打开自己电脑上的QQ。
完成步骤：
```
1,确定自己电脑上的QQ安装在哪里
2,启动cmd
3,进入到启动程序QQ.exe所在的路径。
4,输出qq.exe加回车表示启动qq。
```

解惑：
​	在windows操作系统当中，文件名或者文件夹名是忽略大小写的。

### java概述

语言：人与人交流沟通的表达方式
计算机语言：人与计算机之间进行信息交流沟通的一种特殊语言
Java是一门非常火的计算机语言。（也叫做编程语言）
我们想要让计算机做一些事情，那么就可以通过Java语言告诉计算机就可以了

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051430889.png)

#### Java程序开发运行流程
开发Java程序，需要三个步骤：编写程序，编译程序，运行程序。

### Java语言的发展
三个版本：
Java5.0：这是Java的第一个大版本更新。
Java8.0：这个是目前绝大数公司正在使用的版本。因为这个版本最为稳定。
Java15.0：这个是我们课程中学习的版本。
解惑：
​	我们学的跟工作中使用的版本不太一样啊。会不会影响以后工作呢？
向下兼容。新的版本只是在原有的基础上添加了一些新的功能而已。
举例：
用8版本开发的代码，用11版本能运行吗？必须可以的。
用11版本开发的代码，用8版本能运行吗？不一定。
如果11版本开发的代码，没有用到9~11的新特性，那么用8是可以运行的。
如果11版本开发的代码，用到了9~11的新特性，那么用8就无法运行了。

### Java的三大平台
​	JavaSE、JavaME、JavaEE
1.8.1 JavaSE
​	是其他两个版本的基础。
1.8.2 JavaME
​	Java语言的小型版，用于嵌入式消费类电子设备或者小型移动设备的开发。
​	其中最为主要的还是小型移动设备的开发（手机）。渐渐的没落了，已经被安卓和IOS给替代了。
​	但是，安卓也是可以用Java来开发的。
1.8.3 JavaEE
​	用于Web方向的网站开发。（主要从事后台服务器的开发）
​	在服务器领域，Java是当之无愧的龙头老大。

### Java的主要特性
面向对象
安全性
多线程
简单易用
开源
跨平台
1.9.1 Java语言跨平台的原理
操作系统本身其实是不认识Java语言的。
但是针对于不同的操作系统，Java提供了不同的虚拟机。
虚拟机会把Java语言翻译成操作系统能看得懂的语言。

## java基础语法

### java的注释分为三种

单行注释 //

多行注释：/* */ 多行注释不能嵌套使用的

文档注释 /**     */ 暂时用不到这个

### 关键字

​被Java赋予了特定含义的英文单词。
​当我们在代码中写了关键字之后，程序在运行的时候，就知道要做什么事情了。
注意：关键字很多，不用刻意去记。
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051432739.png)

### class关键字
表示定义一个类。创建一个类。

类：Java项目最基本的组成单元，一个完整的Java项目有可能会有成千上万个类来组成的。

class后面跟随的就是这个类的名字，简称：类名。

在类名后面会有一对大括号，表示这个类的内容。
举例：
```
public class HelloWorld{
}
```
解释：class表示定义类。
类名：HelloWorld
HelloWorld后面的大括号表示这个类的范围。


### 字面量

字面量的作用是：告诉程序员，数据在程序中的书写格式

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051433503.png)

```java
public class Demo {
    public static void main(String[] args) {
        System.out.println(10); // 输出一个整数
        System.out.println(5.5); // 输出一个小数
        System.out.println('a'); // 输出一个字符
        System.out.println(true); // 输出boolean值true
        System.out.println("欢迎来到黑马程序员"); // 输出字符串
    }
}
```

#### 区分技巧
不带小数点的数字都是整数类型的字面量。
只要带了小数点，那么就是小数类型的字面量。
只要用双引号引起来的，不管里面的内容是什么，不管里面有没有内容，都是字符串类型的字面量。
字符类型的字面量必须用单引号引起来，不管内容是什么，但是个数有且只能有一个。
字符类型的字面量只有两个值，true、false。
空类型的字面量只有一个值，null。

### 变量
什么是变量，变量就是程序中，临时存储数据的容器，但是这个容器只能存在一个值

#### 变量的定义格式
数据类型 变量名 = 数据值；

#### 格式详解
数据类型：限定了变量当中能存储什么类型的数据。
如果要存10，那么数据类型就需要写整数类型。
如果要存10.0，那么数据类型就需要写小数类型。
变量名：其实就是这个容器的名字。
当以后想要使用变量里面的数据时，直接使用变量名就可以了。
数据值：真正存储在容器中的数据。
分号：表示语句的结束，就跟以前写作文时候的句号是一样的。

#### 常用的数据类型
整数：int
小数：（浮点数）double
其他数据类型稍后讲解
举例
```java
public class VariableDemo{
public static void main(String[] args){
//定义一个整数类型的变量
//数据类型 变量名 = 数据值;
int a = 16;
System.out.println(a);//16

//定义一个小数类型的变量
double b = 10.1;
System.out.println(b);//10.1
}
}
```


#### 变量的注意事项
变量名不能重复
在一条语句中，可以定义多个变量。但是这种方式影响代码的阅读，所以了解一下即可。
变量在使用之前必须要赋值，也就是初始化。
案例：

```java
public class VariableDemo2{
public static void main(String[] args){
//1.变量名不允许重复
//int a = 10;
//int a = 20;
//System.out.println(a);

//2.一条语句可以定义多个变量
//了解。
//int a = 10, b = 20, c = 20,d = 20;
//System.out.println(a);//?
//System.out.println(b);//?


//3.变量在使用之前必须要赋值
int a = 30;
System.out.println(a);
}
}
```

### 数据类型
基本数据类型
引用数据类型（面向对象的时候再深入学习）

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051435118.png)

说明
e+38表示是乘以10的38次方，同样，e-45表示乘以10的负45次方。
在java中整数默认是int类型，浮点数默认是double类型。

#### 需要记忆以下几点
1. byte类型的取值范围：
	-128 ~ 127
2. int类型的大概取值范围：
	-21亿多 ~ 21亿多
整数类型和小数类型的取值范围大小关系：
double > float > long > int > short > byte
最为常用的数据类型选择：
在定义变量的时候，要根据实际的情况来选择不同类型的变量。
- 比如：人的年龄，可以选择byte类型。
- 比如：地球的年龄，可以选择long类型。
- 如果整数类型中，不太确定范围，那么默认使用int类型。
- 如果小数类型中，不太确定范围，那么默认使用double类型。
- 如果要定义字符类型的变量，那么使用char
- 如果要定义布尔类型的变量，那么使用boolean注意点
- 如果要定义 一个整数类型的变量，不知道选择哪种数据类型了，默认使用int。
- 如果要定义 一个小数类型的变量，不知道选择哪种数据类型了，默认使用double。
- 如果要定义一个long类型的变量，那么在数据值的后面需要加上L后缀。（大小写都可以，建议大写。）
- 如果要定义一个float类型的变量，那么在数据值的后面需要加上F后缀。（大小写都可以）

### 标识符
业内大多数程序员都在遵守阿里巴巴的命名规则。

在day02的资料文件夹中有。

#### 硬性要求：

必须要这么做，否则代码会报错。

* 必须由数字、字母、下划线\_、美元符号$组成。
* 数字不能开头
* 不能是关键字
* 区分大小写的。

#### 软件建议：

如果不这么做，代码不会报错，但是会让代码显得比较low。

#### 小驼峰命名法 

适用于变量名和方法名

* 如果是一个单词，那么全部小写，比如：name
* 如果是多个单词，那么从第二个单词开始，首字母大写，比如：firstName、maxAge

#### 大驼峰命名法 

适用于类名

* 如果是一个单词，那么首字母大写。比如：Demo、Test。
* 如果是多个单词，那么每一个单词首字母都需要大写。比如：HelloWorld

不管起什么名字，都要做到见名知意。

##3# 阿里巴巴命名规范细节：

1. 尽量不要用拼音。但是一些国际通用的拼音可视为英文单词。
1. 正确：alibaba、hangzhou、nanjing
1. 错误：jiage、dazhe
1. 平时在给变量名、方法名、类名起名字的时候，不要使用下划线或美元符号。
1. 错误：\_name
1. 正确：name


### 键盘输入Scanner

键盘录入的实际功能Java已经帮我们写好了，不需要我们自己再实现了，而Java写好的功能都放在了Scanner这个类中，所以，我们只要直接使用Scanner这个类就可以了。
 
使用步骤：
第一步：
导包：其实就是表示先找到Scanner这个类在哪。
第二步：
创建对象：其实就表示申明一下，我准备开始用Scanner这个类了。
第三步：
接收数据：也是真正干活的代码。

```java
//导包，其实就是先找到Scanner这个类在哪 
import java.util.Scanner;
public class ScannerDemo1{     
		public static void main(String[] args){         //2.创建对象，其实就是申明一下，我准备开始用Scanner这个类了。         
		Scanner sc = new Scanner(System.in);         //3.接收数据当程序运行之后，我们在键盘输入的数据就会被变量i给接收了         
		System.out.println("请输入一个数字");             int i = sc.nextInt();         System.out.println(i);     
		}
 }
```


### 输出

```java
常用的输出方式
System.out.println()——作用是可以进行字符串的相加和，字符串和变量相加的时候得到的是字符串，变量和变量相加得到的是变量，且带有换行效果,这个输出本身也能输出常用的标识符,比如说制表符和换行符之类的
System.out.print()——和上面的一样作用，就是没有换行
System.out.printf("标识符"，变量)——和C语言中printf效果一样，不过这里的标识符可以是一个字符串变量，并没有换行效果，换行效果可以通过"\n"实现
```

## 运算符和表达式

### 基础概念

运算符：
就是对常量或者变量进行操作的符号。
比如： + - * / 
表达式：
用运算符把常量或者变量连接起来的，符合Java语法的式子就是表达式。
比如：a + b 这个整体就是表达式。
而其中+是算术运算符的一种，所以这个表达式也称之为算术表达式。

### 算术运算符

就是普通的加减乘除，没什么区别的，不过要注意以下几点

1.整数相除结果只能得到整除，如果结果想要是小数，必须要有小数参数。
2.小数直接参与运算，得到的结果有可能是不精确的。


### 隐式转换

系统自动进行的类型转换，
就是把一个取值范围小的数据或者变量，赋值给另一个取值范围大的变量。此时不需要我们额外写代码单独实现，是程序自动帮我们完成的。

简单的记忆
就是小的给大的，可以直接给。

取值范围小的，和取值范围大的进行运算，小的会先提升为大的，再进行运算。
byte、short、char三种类型的数据在运算的时候，都会直接先提升为int，然后再进行运算。

### 强制转换
概念：
如果要把一个取值范围大的数据或者变量赋值给另一个取值范围小的变量。是不允许直接操作。
如果一定要这么干，就需要加入强制转换。
 
书写格式：
目标数据类型 变量名 = （目标数据类型）被强转的数据；
简单理解：
要转成什么类型的，那么就在小括号中写什么类型就可以了。
**强制转换有可能会导致数据发生错误。（数据的精度丢失）**


### 字符串得加操作

核心技巧：
当+操作中出现字符串时，此时就是字符串的连接符，会将前后的数据进行拼接，并产生一个新的字符串。
当连续进行+操作时，从左到右逐个执行的。

我们需要注意的是，只有字符串才会互相连接，如果不是字符串那么就是做加法运算

案例1
```java
1 + 2 + "abc" + 2 + 1
结果：“3abc21”
解释：
第一步：1 + 2 。在这个过程中，没有字符串参与的，所以做的是加法运算，结果为3。
第二步：3 + "abc"。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc"。
第三步："3abc" + 2。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc2"。
第四步："3abc2" + 1。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串“3abc21”
```

案例2
```java
String name = "黑默丁格";
System.out.println("我的名字是" + name);
结果： 我的名字是黑默丁格
解释：当字符串跟变量相加的时候，实际上是跟变量里面的值进行拼接。
```

### 字符的加操作

规则：
当+操作中出现了字符，会拿着字符到计算机内置的ASCII码表中去查对应的数字，然后再进行计算。

```java
char c = 'a';
int result = c + 0;
System.out.println(result);//97
```

**最后输出的并不是一个字符，而是一个数字**

### 算术运算符的计算
注意点：
/ 和 % 的区别：他们两个都是做除法运算，/取结果的商。% 取结果的余数。
整数操作只能得到整数，如果想要得到小数，必须有浮点数参与运算。
算术运算符的高级用法：
是以+为例进行的讲解，其余减法，乘法，除法的运算规则也是一样的。
特例：字符串只有+操作，没有其他操作。

### 自增自减运算符

++：就是把变量里面的值+1

--：就是把变量里面的值-1

这两个运算符放在前面，就是先运算这个自增运算
如果放在后面就先运算与其相连接的其他的运算，在运算这个

## 逻辑运算符

& 和 | 的使用：
&：逻辑与（而且）
两边都为真，结果才是真，只要有一个为假，那么结果就是假。
|：逻辑或（或者）
两边都为假，结果才是假，只要有一个为真，那么结果就是真。

java中也是会存在逻辑短路的问题，但是逻辑短路问题不是存在于这个&和|中，而是存在&&和||里两个是不一样的

```java
// &  //两边都是真，结果才是真。
System.out.println(true & true);//true
System.out.println(false & false);//false
System.out.println(true & false);//false
System.out.println(false & true);//false

System.out.println("===================================");

// | 或  //两边都是假，结果才是假，如果有一个为真，那么结果就是真。
System.out.println(true | true);//true
System.out.println(false | false);//false
System.out.println(true | false);//true
System.out.println(false | true);//true
```


^（异或）的使用：
在以后用的不多，了解一下即可。
计算规则：如果两边相同，结果为false，如果两边不同，结果为true
代码示例：

分类： && ||

&&：
运算结果跟&是一模一样的，只不过具有短路效果。
||：
运算结果跟|是一模一样的。只不过具有短路效果。
**逻辑核心：**
当左边不能确定整个表达式的结果，右边才会执行。
当左边能确定整个表达式的结果，那么右边就不会执行了。从而提高了代码的运行效率。

### 三元运算符

又叫做：三元表达式或者问号冒号表达式。
**格式：**
关系表达式 ？ 表达式1 ：表达式2 ；
**计算规则：**
计算关系表达式的值。
如果关系表达式的值为真，那么执行表达式1。
如果关系表达式的值为假，那么执行表达式2。
**注意点：**
三元运算符的最终结果一定要被使用，要么赋值给一个变量，要么直接打印出来。

```java
public class OperatorDemo12 {
    public static void main(String[] args) {
        //需求：求两个数的较大值
        int a = 10;
        int b = 20;

        //格式：关系表达式 ？ 表达式1 ： 表达式2 ；
        //注意点：
        //三元运算符的最终结果一定要被使用。
        //要么赋值给一个变量，要么直接输出。
       int max =  a > b ? a : b ;
        System.out.println(max);


        System.out.println(a > b ? a : b);
    }
}
```


## 数组

### 数组的定义

格式一：
数据类型 [] 数组名
比如：int [] array
格式二：
数据类型 数组名 []
比如： int array []

详解：
数据类型：限定了数组以后能存什么类型的数据。
方括号：表示现在定义的是一个数组。
数组名：就是一个名字而已，方便以后使用。

注意点：

方法括号跟数组名，谁写在前面，谁写在后面都是一样的。
平时习惯性使用第一种方式

### 数组的静态初始化
完整格式：
>数据类型[] 数组名 = new 数据类型[]{元素1，元素2，元素3，元素4...};

比如：
```java
int[] arr = new int[]{11,22,33};
double[] arr = new double[]{1.1,1.2,1.3};
```


**格式详解：**

数据类型：限定了数组以后能存什么类型的数据。

方括号：表示现在定义的是一个数组。其实类似于C语言中的指针了，用来和整型变量做区分

数组名：其实就是名字而已，方便以后使用，在起名字的时候遵循小驼峰命名法。
		arr namesArr

new：就是给数组在内存中开辟了一个空间。

数据类型：限定了数组以后能存什么类型的数据。
前面和后面的数据类型一定要保持一致。

int[] arr = new double[]{11,22,33};//错误写法

方括号：表示现在定义的是一个数组。

大括号：表示数组里面的元素。元素也就是存入到数组中的数据。


**注意点：**
多个元素之间，一定要用逗号隔开。
数组一旦创建后，长度不能改变

简化格式:
数据类型[] 数组名 = {元素1，元素2，元素3，元素4...};
比如：
```java
int[] array = {1,2,3,4,5};
double[] array = {1.1,1.2,1.3};
```

### 数组的地址

```java
int[] arr = {1,2,3,4,5};
System.out.println(arr);//[I@6d03e736
​
double[] arr2 = {1.1,2.2,3.3};
System.out.println(arr2);//[D@568db2f2
```

打印数组的时候，实际出现的是数组的地址值。
数组的地址值：就表示数组在内存中的位置。

```
以[I@6d03e736为例：
[ ：表示现在打印的是一个数组。
I：表示现在打印的数组是int类型的。
@：仅仅是一个间隔符号而已。
6d03e736：就是数组在内存中真正的地址值。（十六进制的）

但是，我们习惯性会把[I@6d03e736这个整体称之为数组的地址值。
地址值对于我们来京，作用不大，简单了解。
```

### 数组的动态初始化

**格式：**
数据类型[] 数组名 = new 数据类型[数组的长度];

这里面的数组的长度可以是一个变量

**数组的默认初始化值：**
整数类型：0
小数类型：0.0
布尔类型：false
字符类型：'\ u0000'
引用类型：null

```java
//1.定义一个数组，存3个人的年龄，年龄未知
int[] agesArr = new int[3];
​
​
//2.定义一个数组，存班级10名学生的考试成绩，考试成绩暂时未知，考完才知道。
int[] scoresArr = new int[10];
```

### 数组的两种初始化区别

静态初始化：int[] arr = {1,2,3,4,5};
动态初始化：int[] arr = new int[3];
静态初始化：手动指定数组的元素，系统会根据元素的个数，计算出数组的长度。
动态初始化：手动指定数组长度，由系统给出默认初始化值。
**使用场景：**
只明确元素个数，但是不明确具体的数据，推荐使用动态初始化。
已经明确了要操作的所有数据，推荐使用静态初始化。
**举例：**
```java

使用数组来存储键盘录入的5个整数。
int[] arr = new int[5];
将全班的学生成绩存入数组中，已知学生成绩为：66,77,88,99,100
int[] arr = new int[5];
arr[0] = 66;
arr[1] = 77;
... 虽然可以实现，但是太麻烦了。
建议使用静态初始化：int[] arr = {66,77,88,99,100};
```

## 方法

### 方法的概述 

```
方法（method）是程序中最小的执行单元
注意：
方法必须先创建才可以使用，该过程成为方法定义
方法创建后并不是直接可以运行的，需要手动使用后，才执行，该过程成为方法调用

方法在哪一个类里调用，我们就最好在哪一个类里面写这个函数
```

**定义格式**
```java
public static void 方法名 (   ) {
	// 方法体;
}
```

**范例**
```java
public static void method (    ) {
	// 方法体;
}
```

**调用格式**
```java
方法名();
```

**范例**
```java
method();
```
方法必须先调用，在使用，否则程序将会报错

### 形参和实参

1. 形参：方法定义中的参数

​          等同于变量定义格式，例如：int number

2. 实参：方法调用中的参数

​          等同于使用变量或常量，例如： 10  number

### 方法的注意事项

注意事项
方法不能嵌套定义
void 无返回值，可以省略return ，也可以单独写个return用于退出程序，但是后面不要跟内容

### 方法的重载

```
方法重载概念
方法重载指同一个类中定义的多个方法之间的关系，满足下列条件的多个方法相互构成重载
多个方法在同一个类中
多个方法具有相同的方法名
多个方法的参数不相同，类型不同或者数量不同
注意：
重载仅对应方法的定义，与方法的调用无关，调用方式参照标准格式
重载仅针对同一个类中方法的名称与参数进行识别，与返回值无关，换句话说不能通过返回值来判定两个方法是否相互构成重载
```

## 类
### random类

Random跟Scanner一样，也是Java提前写好的类，我们不需要关心是如何实现的，只要直接使用就可以了。

1. 导包
```java
import java.util.Random;
导包的动作必须出现在类定义的上边。
```

2. 创建对象
```java
Random r = new Random ();
上面这个格式里面，只有r是变量名，可以变，其他的都不允许变。
```

3. 生成随机数
```java
int number = r.nextInt(随机数的范围);
上面这个格式里面，只有number是变量名，可以变，其他的都不允许变。
随机数范围的特点：从0开始，不包含指定值。比如：参数为10，生成的范围[0,10)
```

4. 代码示例
```java
//1.导包
import java.util.Random;

public class RandomDemo1 {
    public static void main(String[] args) {
        //2.创建对象
        Random r = new Random();
        //3.生成随机数
        int number = r.nextInt(100);//包左不包右，包头不包尾
        //0 ~ 99
        System.out.println(number);

    }
}
```

### Scanner类

我们可以通过Scanner类进行创建输入函数
```java
Scanner 变量名 = new Scanner(System.in);

数据类型 = 变量名.next数据类型();
```

```
其中
nextInt()接受整形
nextDouble()接受double型


next()接受字符串型
nextLine()同样接受字符串型,
这些有什么区别呢
next()接受字符串型,但是遇到空格,制表符回车就会自动终止
nextLine()同样接受字符串型,并且可以同时接受这个空格,遇到回车才会终止
两者混用会造成这个空间产生错误的输入,因为你输入的回车和空格虽然没被接受,但是并没有消失,只是在缓冲区里面而已.
```

# 面向对象

## 面向对象的介绍

为什么用面向对象敲代码呢
因为这个复合我们人们的处理事物的习惯
我们重点学习的是什么
学习获取已有对象 ，并使用，学习如何自己创建对象，并使用

主要学习
1. 设计对象并使用
2. 封装
3. this关键字
4. 构造方法
5. 标准JavaBean
6. 对象内存图
7. 补充知识：成员变量，局部变量

## 类和对象

类和对象：
类就是我们的对象设计图：是对象共同特征的描述
对象就是一个根据护设计图具体存在的示例

**定义方式**
```java
public class 类名{
    1. 成员变量（代表属性，一般是名词）
    2. 成员方法（代表行为，一般是动词）
    3. 构造器
    4，代码块
    5. 内部类
}
```

构造方式
类名 + 变量名 = new 类名（）

```java
public class 类名 {
    // 成员变量
    变量1的数据类型 变量1；
    变量2的数据类型 变量2;
    …
    // 成员方法
    方法1;
    方法2;	
}
```


### 对象的使用
创建对象的格式：
	类名 对象名 = new 类名();
调用成员的格式：
	对象名.成员变量
	对象名.成员方法();

```java
/*
    创建对象
        格式：类名 对象名 = new 类名();
        范例：Phone p = new Phone();

    使用对象
        1：使用成员变量
            格式：对象名.变量名
            范例：p.brand
        2：使用成员方法
            格式：对象名.方法名()
            范例：p.call()
 */
public class PhoneDemo {
    public static void main(String[] args) {
        //创建对象
        Phone p = new Phone();

        //使用成员变量
        System.out.println(p.brand);
        System.out.println(p.price);

        p.brand = "小米";
        p.price = 2999;

        System.out.println(p.brand);
        System.out.println(p.price);

        //使用成员方法
        p.call();
        p.sendMessage();
    }
}
```

### 类和对象的补充注意事项

1. 类名首字母建议大写，需要见名知意，尽量采用驼峰命名法
2. 一个java文件中，可以定义多个class类，且只能一个类是public修饰，而且public修饰的类名，必须成为代码文件名
3. 实际开发中建议一个文件定义一个文件class类
4. 成员变量的完整定义格式是：修饰符 数据类型，变量名称=初始化值；一般无需指定初始化值，存在默认值

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051501222.png)

## 封装
封装告诉我们拿到一个对象后,如何正确设置属性和方法

涉及到多对象,比如说人画圆这个行为
人是一个对象,圆也是一个对象,画是一个行为
那么我们怎么设置这个人画圆的这个行为呢

我们或许会直接认为,这个画圆是属于这个人的一个行为,但实际上并不是的,人画圆这个是属于圆这个类的行为

封装
对象代表什么,就要封装对应的数据,并提供数据对应的行为

另一个例子,人关门,并不是人去关门,而是门本身提供了关闭和打开的方法
人调用了门关闭的方法,门就自己关上了

### 封装的好处

封装的好处
sum公司给我们已经设计好了很多的类,所以很多的类我们都不需要进行写,我们只需要进行调用就好了
对象代表什么,就得封装对应的数据,并记录其对应的行为
可以让我们的编程变得更加简单,可以少学,少记,我们只需要会找就行
这也体现了这个面向对象的思想,我们在操作的时候,我们只需要这个对象是什么就行了,至于实现这个的过程我们不用考虑了


### private

private是一个关键字
是一个权限修饰符
可以修饰成员,成员变量,和成员方法
被private修饰的成员只能在本类中进行访问

### public

public和private是相反的,意思是所有的域内都可以使用这个方法,或这个变量

和c++类似,对于一个类,我们在私有域中定义这个变量,然后在公共域中定义这个获取方法,和赋值方法

常用的是get和set一个是赋值一个是获得

### this关键字

this修饰的变量用于指代成员变量，其主要作用是（区分局部变量和成员变量的重名问题）
- 方法的形参如果与成员变量同名因为例如name,age什么的不好换名字,最好是用这个,用的话又会出现重名的情况，不带this修饰的变量指的是形参，而不是成员变量
- 方法的形参没有与成员变量同名，不带this修饰的变量指的是成员变量

```java
public class Student {
    private String name;
    private int age;

    public void setName(String name) {
        name = name;//name先到最近的成员变量里去找这个name,如果有的话就用,没有的话就去全局变量里走
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getAge() {
        return age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
```

成员的就近原则
```java
public class gf{

    int age=5;
    public void fun(){
        int age=10;
        System.out.println(age);//会打印这个10,我们可以用this这个成员变量来定位这个5
    }
}

```

## 构造方法
构造方法也叫做构造器,构造函数.
作用是在创建对象的时候给成员变量进行赋值的
创造对象的时候,虚拟机会自动调用这个构造方法,作用是给成员变量进行初始化的.
```java
public class Student{
    修饰符 类名(参数){
        方法体;
    }
}
```

特点
1. 方法名与类名相同,大小写也要一致
2. 没有返回值类型,连void都没有
3. 没有具体的返回值(不能由return带回返回结果)

构造方法是不能自己去调用的,而是创建对象的时候由虚拟机进行调用,不能手动的调用构造方法
每创建一次对象,就会调用一次构造方法

### 无参构造方法


观察下面的两种方法我们可以发现我们在使用这个构造新的类的时候,会自动执行这个构造函数,即使我们并没有传递参数


构造方法类的测试.java
```java
package test;
public class 构造方法类的测试 {
    public static void main(String[] args){
        构造方法类 arr = new 构造方法类();
    }
}
```

构造方法类.java
```java
package test;

public class 构造方法类 {
    int age;
    int id;
    public 构造方法类() {
        System.out.println("看看我输出了没");
    }
}
```

### 有参构造方法
有参构造我们在建立对象的时候同时对这个对象进行赋值

```java
/*
    学生类
 */
class Student {
    private String name;
    private int age;

    public Student() {}

    public Student(String name) {
        this.name = name;
    }

    public Student(int age) {
        this.age = age;
    }

    public Student(String name,int age) {
        this.name = name;
        this.age = age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*
    测试类
 */
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s1 = new Student();
        s1.show();

        //public Student(String name)
        Student s2 = new Student("林青霞");
        s2.show();

        //public Student(int age)
        Student s3 = new Student(30);
        s3.show();

        //public Student(String name,int age)
        Student s4 = new Student("林青霞",30);
        s4.show();
    }
}
```

### 构造方法的注意事项
构造方法的创建
- 如果没有定义构造方法，系统将给出一个默认的无参数构造方法
- 如果定义了构造方法，系统将不再提供默认的构造方法
构造方法的重载
- 如果自定义了带参构造方法，还要使用无参数构造方法，就必须再写一个无参数构造方法

```java
public Student() {}

    public Student(String name) {
        this.name = name;
    }
```

推荐的使用方式
无论是否使用，都手工书写无参数构造方法
一旦你自己写了这个有参的构造方式,那么虚拟机就不会给你加上这个无参数的构造方式了,所以这个时候需要你自己去添加了

```java
不管你用不用,我们都要去写玩这个无参构造和带有全部参数的有参构造写出来
    public Student(String name,int age) {
        this.name = name;
        this.age = age;
    }
```

重要功能！
可以使用带参构造，为成员变量进行初始化
示例代码

```java
/*
    学生类
 */
class Student {
    private String name;
    private int age;

    public Student() {}

    public Student(String name) {
        this.name = name;
    }

    public Student(int age) {
        this.age = age;
    }

    public Student(String name,int age) {
        this.name = name;
        this.age = age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*
    测试类
 */
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s1 = new Student();
        s1.show();

        //public Student(String name)
        Student s2 = new Student("林青霞");
        s2.show();

        //public Student(int age)
        Student s3 = new Student(30);
        s3.show();

        //public Student(String name,int age)
        Student s4 = new Student("林青霞",30);
        s4.show();
    }
}
```


## 对象的内存图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051507602.png)


java的内存分配介绍
栈
堆
方法区
本地方法栈
寄存器

1. 方法区 运行一个类的时候，这个类的字节码文件加载的时候就会进入内存空间
2. 栈内存 方法运行时所进入的内存变量也是在这里,方法里面的变量会存放到这个区域
3. 堆内存 new出来的东西会在这块内存中开辟空间并产生地址

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051507721.png)


对于字符型的数据,其实其并不是java的基本数据类型,而是一种类
方法区的变量执行完之后内存会自动的进行释放.

### 基本和引用数据类型
定义一个基本数据类型我们是在栈空间中进行开辟空间的,数据值是存放在自己的空间中,不会和其他空间产生关系,特点是,赋值给其他变量,也是在赋值的真实的值

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051508745.png)


1. 我们创建的对象,数组,字符等都是引用数据类型,,就是使用其他空间的数据进行使用.
2. 引用数据类型的数据值是存储在其他空间中的,自己空间中存储的是地址值
3. 特点是赋值给其他变量,赋值的是地址值

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051509986.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051509062.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051509354.png)



### this的内存原理
1. this的作用是区分局部变量,和成员变量
为什么可以这样区分呢
2. this的本质就是代表方法调用者的地址值
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051510207.png)

### 成员变量和局部变量的区别
成员变量,是类中方法外的变量
局部变量是方法里面的变量

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051510895.png)


# 字符串

## API
API就是一种别人已经写好的东西，我们不需要自己会写，我们只需要知道怎么使用就行
java中的API
指的就是 JDK 中提供的各种功能的 Java类，这些类将底层的实现封装了起来，我们不需要关心这些类是如何实现的，只需要学习这些类如何使用即可，我们可以通过帮助文档来学习这些API如何使用。
API帮助文档，是帮助我们程序员查询和使用的一个参考文档
## String字符串
### String类概述

String 类代表字符串，Java 程序中的所有字符串文字（例如“abc”）都被实现为此类的实例。也就是说，Java 程序中所有的双引号字符串，都是
String 类的对象。String 类在 java.lang 包下，所以使用的时候不需要导包！

java.lang包是java的核心包,所以我们不需要进行导包


### String类的特点 

这里的不能进行修改时指，即使你修改了 ，但是原来存放数据的那一段空间仍然是存在的，并且不能够进行修改。
* 字符串不可变，它们的值在创建后不能被更改,**两个字符串进行拼接后是产生了一个新的字符串.**
* 虽然 String 的值是不可变的，但是它们可以被共享
* 字符串效果上相当于字符数组( char\[\] )，但是底层原理是字节数组( byte\[\] )
  java不会字符串,开发就会凉一半

字符串常见操作

1. String
1. StringBuilder
1. StringJonier
1. StringBuffer
1. Pattern
1. Matcher
### 字符串的创建

第一种我们直接进行赋值创建
第二种我们通过new关键字进行创建类对象

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051513448.png)

直接创建
```java
        String s1 = "qiukehao1";
        System.out.println(s1);
```

创建空字符串
```java
	        String s2 = new String();
	        System.out.println("qiu" + s2 + "kehao2");
```
创建一个字符串在赋值给另一个字符串,脱裤子放屁 ,没啥用
```java
        String s3 = new String("qiukehao3");//IDE里提示这个可以不写
        System.out.println(s3);
```

根据字符数组进行构建,这种适合以后如果我们想修改字符串的话我们可以通过这种方式,先修改字符数组的元素,在修改字符串的元素.
```java
        char[] ch = new char[] { 'q', 'k', 'h' };
        String s4 = new String(ch);
        System.out.println(s4);
```


根据字节数组来进行构建,这个构建的并不是99,98,.97的字符串,而是根据这个数字的大小去ASICC码中进行寻找.这个的应用场景是,我们以后在网络中进行传递的是字节信息,但是字节信息我们看不懂啊,所以我们可以通过这个字符串的转换来进行应用.
```java
        byte[] bys = { 99, 98, 97 };
        String s5 = new String(bys);
        System.out.println(s5);
```


### 创建方式的区别

第一种我们直接进行赋值创建
第二种我们通过new关键字进行创建类对象

**new出来的对象是放在堆区里面**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051515861.png)


我们通过直接赋值产生的字符串,对于新创建的字符串,并不是直接去串池去申请空间,而是去串池里去找这个有没有相同的字符串,如果有的话,我们就将这个字符串的地址进行传递回来.

**优点是:简单,节约内存,缺点是会造成复用
第二种是会浪费内存,但是不会造成复用**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051515831.png)


### 字符串的比较
```
==号比较的到底是什么
如果是基本数据类型,我们比较的是具体的数据值,
如果是引用数据类型,我们比较的是两个变量的地址值
所以你直接赋值的字符串可以进行==比较,因为相同的字符串的地址是相同地址的,但是如果是通过new出来的字符串我们可以通过这个==进行判断,虽然值是相同的,但是地址不相同,所以无法通过这个==进行判断

那么我们如何比较字符串呢
我们可以通过boolean 型函数equal进行比较,public boolean equals(String s) 比较两个字符串内容是否相同、区分大小写
```

```java
public class StringDemo02 {
    public static void main(String[] args) {
        //构造方法的方式得到对象
        char[] chs = {'a', 'b', 'c'};
        String s1 = new String(chs);
        String s2 = new String(chs);
        //直接赋值的方式得到对象
        String s3 = "abc";
        String s4 = "abc";
        //比较字符串内容是否相同
        System.out.println(s1.equals(s2));
        System.out.println(s1.equals(s3));
        System.out.println(s3.equals(s4));
    }
}
```

#### 忽略大小写的比较
**equalsIgnoreCase是我们可以进行忽略大小写的比较,这个忽略是忽略的英文,不能忽略中文的**

### substring方法

substring方法是我们进行截取一个字符串所用的
s.substring(1,3)就是截取0~3的字符串,返回一个字符串
s.substring(7)就是截取7之后的字符串

## StringBuilder
StringBuilder可以看作一个容器，创建以后里面的内容是可以变化的
作用是，提高字符串的操作效率

字符串的拼接，由于字符串是不可以变化的，我们字符串的拼接本质是创建了一个新的字符串，所以当拼接特别长的时候就会产生特别多的无用字符串

### StringBuilder的常见方法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051517358.png)



打印这个StringBuilder创建的对象，我们并不是打印的地址，这个和我们之前学打的对象并不太一样，因为这个StringBuilder是java已经写好的类，java在低层对他做了一些特殊处理，打印对象，不是地址值，而是属性值

注意这个StringBuilder并不是一个字符串，而是类似于一个容器，我们利用这个容器进行处理字符串，用完之后就把他给抛弃就行了

我们一般是在字符串的拼接和反转的时候用这个StringBuilder的，其他情况下我们还是用正常的String就行

### 链式编程
当我们在调用一个方法的时候，不需要用变量接受他的结果，可以继续调用其他方法

比如说下面这个

```java
public class StringBuilderDemo4 {
    public static void main(String[] args) {
        //1.创建对象
        StringBuilder sb = new StringBuilder();

        //2.添加字符串
        sb.append("aaa").append("bbb").append("ccc").append("ddd");

        System.out.println(sb);//aaabbbcccddd

        //3.再把StringBuilder变回字符串
        String str = sb.toString();
        System.out.println(str);//aaabbbcccddd

    }
}
```

### 判断字符串是否是对称的
```java
package StringPratice;
import java.util.Scanner;
public class 判断字符串是否对称 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("请输入你要判断的字符串");
        String str = input.next();
        StringBuilder s = new StringBuilder(str);

        String str2 = s.reverse().toString();
        if(str.equals(str2)){
            System.out.println("是");
        }else System.out.println("否");

    }
}
```

### 字符串的拼接
```java
package StringPratice;

public class 字符串的拼接 {
    public static void main(String[] args) {
        int[] arr = {1,2,3,34};
        StringBuilder s = new StringBuilder("[");
        for(int i=0;i<arr.length;i++){
            if(i<arr.length-1){
                s.append(arr[i]).append(",");
            }else s.append(arr[i]);
        }
        String s1 = s.append("]").toString();
        System.out.println(s1);
    }
}

```

## StringJoiner

StringJoiner跟StringBuilder一样，也可以看成是一个容器，创建之后里面的内容是可变的。
作用：提高字符串的操作效率，而且代码编写特别简洁，但是目前市场上很少有人用。 
JDK8出现的

可以指定这个字符串之间的间隔元素，必须指定，StringJoinner是没有空参构造的。

```java
//1.创建一个对象，并指定中间的间隔符号
StringJoiner sj = new StringJoiner("---");
//2.添加元素
sj.add("aaa").add("bbb").add("ccc");
//3.打印结果
System.out.println(sj);//aaa---bbb---ccc
```

第一个是间隔符号，第二个是开始符号，第三个是结束符号

```java
//1.创建对象
StringJoiner sj = new StringJoiner(", ","[","]");
//2.添加元素
sj.add("aaa").add("bbb").add("ccc");
int len = sj.length();
System.out.println(len);//15
//3.打印
System.out.println(sj);//[aaa, bbb, ccc]
String str = sj.toString();
System.out.println(str);//[aaa, bbb, ccc]
```

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051519863.png)

## 关于字符串的扩展
字符串存储的内存原理
		String s = “abc”；直接赋值
特点：
		此时字符串abc是存在字符串常量池中的。
		先检查字符串常量池中有没有字符串abc，如果有，不会创建新的，而是直接复用。如果没有abc，才会创建一个新的。
		所以，直接赋值的方式，代码简单，而且节约内存


== 比较的到底是什么
如果比较的是基本数据类型：比的是具体的数值是否相等。
如果比较的是引用数据类型：比的是地址值是否相等。
结论：== 只能用于比较基本数据类型。不能比较引用数据类型。

#### 字符串拼接的原理
拼接的底层原理

没有变量的拼接和有变量的拼接
没有变量的拼接
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051520119.png)

有变量的拼接，利用了StringBuildder容器，我们先把字符串放在这个容器里，然后在转化为这个字符串
同时这个串池里面也放的有这个要拼接的字符元素
每次申请都会申请创建一个StringBuildder容器，导致这个效率很低

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051520510.png)


JDK8以后我们做了一个优化，我们会先预估分析，比如说我们拼接了三个对象，我么会先进行预估创建一个数组，将这些字符串存到这个数组里，然后在将这个数组转化字符串

### StringBuilder提高效率的原理图解
StringBuilder创建的字符串对象是new出来的，所以这个是一个独立的空间，我们不能随便的利用==比较这个引用的数据类型

如果没有变量参与，都是字符拆还能直接相加，编译之后就是拼接之后的结果，会复用串池中的字符串
如果有变量参与，每一行拼接的代码，都会在内存中创建新的字符串，浪费内存
所有要拼接的内容都会往StringBuilder中放，不会创建很多无用的空间，节约内存

**只要有变量我们就是用new出来的**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051521071.png)

**如果不是变量的拼接**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304051521267.png)



# 集合

数组的长度是固定的，而这个集合的长度就是可以进行变化的
是一个容器

集合刚开始创建的时候，长度为0，之后我们每次添加一个元素，集合都会**自动进行扩容**，我们只需要添加元素就行了

> 数组

数组可以存放基本数据类型,以及引用数据类型

> 集合

集合只能存放引用数据类型,如果我们真的需要存放这个数据类型,我们可以将这个基本数据类型转化为包装类

> 集合和数组的区别

1. 添加元素的时候自动扩容
2. 删除的时候自动缩小
3. 它只能存放引用数据类型

## 常见的集合ArrayList

这个类是定义在java.util目录下的,所以我们使用的时候要进行导包

> 定义方法

1. JDK7以前的构造方法
ArrayList< String> list = new ArrayList< String>();
2. JDK7以后的方法
ArrayList< String> list = new ArrayList<>();

**相比之下就是后面的尖括号包括的数据类型没了**

直接打印这个我们输出的是两个中括号

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304061011407.png)


 > 添加

添加的时候是用逗号来进行分隔的
**添加的是什么类型我们加在尖括号里添加什么内容,同时如果我们想要添加这个对象,我们只需要将这个尖括号里面的数据类型转化为对象名就行了**
```java
 package study.demo;

import java.util.ArrayList;

public class 集合 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("qiu");
        list.add("ke");
        list.add("hao");
        System.out.println(list);
    }
}
输出: [qiu, ke, hao]
```


> 删除

remove("字符串");删除指定的字符串,然后返回布尔值
```java
boolean index = list.remove("qiu");
System.out.println(index);
// 输出结果是
true
[ke, hao]
```

remove(数字);删除指定的索引,返回被删除的字符串
先删除这个qiu,返回true,然后删除ke,返回科
```
ke
true
[hao]
```

```java
package study.demo;

import java.util.ArrayList;

public class 集合 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("qiu");
        list.add("ke");
        list.add("hao");
        boolean index = list.remove("qiu");
        String s = list.remove(0);
        System.out.println(s);
        System.out.println(index);
        System.out.println(list);
    }
}

```


> set修改指定索引的元素,返回被修改的元素

```java
        String s2 = list.set(0, "lixia");//将最后的hao替换为lixia
        System.out.println(s2);
```

```
hao
ke
true
[lixia]
```

> get 获取元素返回指定索引处的元素

```java
        System.out.println(list.get(0));
```

> 返回集合的长度

```java
        System.out.println(list.size());
```

### 添加基本数据类型

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304061105337.png)


IDEA会自动关联这些,只需要写出这个基本数据类型,然后我们后面就有包装类型的选项

### 注意点
我循环进行添加元素到这个集合的时候**要注意**这个集合的遍历次数并不是这个这个集合的长度,因为这个集合的长度是不断变化的

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304061113072.png)

> 集合的传参是 ArrayList<数据类型> 变量名字

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304061123240.png)


# 学生管理系统
## 注意事项，
### 1. 我们在写这个switch case的时候我们做出的选择最好用字符类型，可以增加我们的代码的健壮性

```java
int choice=0;  
while(choice!=6){  
    menu();  
    System.out.println("请输入你的选择");  
    choice = input.nextInt();  
    switch (choice){  
        case 1:  print(list);  break;        
        case 2:  addInformation(list);  print(list);  break;        
        case 3:  deleteInformation(list); print(list);  break;        
        case 4:  adjustInformation(list); print(list); break;        
        case 5:  searchInformation(list); break;        
        default: break;  
    }  
}
```

改为下面的这种
```java
String choice=0;  
while(choice!=6){  
    menu();  
    System.out.println("请输入你的选择");  
    choice = input.nextInt();  
    switch (choice){  
        case "1":  print(list);  break;        
        case "2":  addInformation(list);  print(list);  break;        
        case "3":  deleteInformation(list); print(list);  break;        
        case "4":  adjustInformation(list); print(list); break;        
        case "5":  searchInformation(list); break;        
        default:   System.out.println("没有这个选择");break;  
    }  
}
```

### 遇到while循环内嵌套了switch此时我们如果想终止这个循环我们可以进行对循环的命名
我们正常的break都是跳出的是本层循环,我们可以通过任意的名字加一个冒号来为循环进行命名,然后我们break这个循环我们就可以调出最外面的循环

```java
loop: while(choice!=6){  
    menu();  
    System.out.println("请输入你的选择");  
    choice = input.nextInt();  
    switch (choice){  
        case "1":  print(list);  break;        
        case "2":  addInformation(list);  print(list);  break;        
        case "3":  deleteInformation(list); print(list);  break;        
        case "4":  adjustInformation(list); print(list); break;        
        case "5":  searchInformation(list); break;        
        default:   System.out.println("没有这个选择");break loop;  
    }  
}
```

### exit
System.exit(0)这一行代码我们可以直接终止这个程序


### 封装

我们如果传递的参数很多的时候,我们这个时候一般不是直接进行一个一个的传参而是我们可以通过这个构建一个新的对象来进行传参,然后传递这个对象就可以了

### 多个java类之间的练习

在这个小项目里面我们有两个主需求,一个是登录一个是管理,我们如何在登录的java类里面去管理这个管理呢,我们可以新建一个这个管理的对象,然后把管理的那个java类的main方法改成其他名字其中的String[] args给删去,然后我们进行调用这个方法的名字就行了

```java

public class 学生类测试 {  
    public static void startSysterm(){  
        Scanner input = new Scanner(System.in);  
        //本身就有信息  
        //引用数据类型本身就是在传递地址  
        ArrayList<学生类> list = new ArrayList<>();  
        学生类 s1 = new 学生类("B5081","邱科豪","20","河南");  
        学生类 s2 = new 学生类("B5082","吴文博","21","甘肃");  
        学生类 s3 = new 学生类("B5083","沈振鸿","20","徐州");  
        学生类 s4 = new 学生类("B5084","陆一飞","19","无锡");
        -------            
	    然后这里我们调用一堆方法就行了
	    -------
    }
}

System.out.println("登录成功进入学生管理系统");  
学生类测试 ss = new 学生类测试();  
ss.startSysterm();
```


# 面向对象的进阶

## static
### 静态变量
> 举例

我们定义了一个学生类,然后通过这个类创建多个学生对象,每个学生对象有一个属性是年龄,姓名,性别和老师,

这些学生对象有一些属性是各不相同的,但是也有一个属性是公有的,就是这个老师的属性,这些学生对应的老师是相同的,

我们如果要给这些学生对象进行赋值的话,那么久太麻烦了,所以我们引入static关键字,通过这个关键字我们可以实现一个变量被多个对象所共有,同时我们的这个static定义的变量还可以直接通过类名进行访问

比如我们定义了一个student类,然后里面的tearchname是static类型的,然后我们就可以直接
student.teachname进行访问变量

static修饰符,是修饰这个变量属于这个类,而不是属于对象

**static的关键特点**
1. 其被改类所有对象共享
2. 可以通过类名调用,我们推荐这种
3. 也可以被对象名调用

### 内存分析

这个static定义的关键字的对象存放到堆区的一个静态空间中,

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111456616.png)


### 静态方法

被static修饰的成员变量,叫做静态变量

被static修饰的成员方法,叫做静态方法
**特点**
1. 多用于测试类和工具类中
2. Javabean类中很少会用
**调用方式**
1. 类名调用
2. 对象名调用

### 三种不同的类的区别

1. JavaBean是用来描述一类事物的类,比如student ,user
2. 测试类用来检查其他类是否书写正确,带有main方法的类,是程序的入口
3. 工具类,不是用来描述一些事物的,而是帮我们做一些事情的类

### 工具类

1. 类名要见名知意
2. 私有化构造方法,**因为这个工具类,不是用来描述一些事物的,你创建这个工具类的对象,没有意义,所以我们要私有化,防止外界调用**
3. 简单来说这个工具类就是我们封装的一系列的函数,我们可以直接进行使用,例如这个.length这个函数

### static的注意事项

1. 静态方法只能访问静态变量和静态方法
2. 非静态方法可以访问静态变量或者静态方法,也可以访问非静态的成员变量和非静态的成员方法
3. 静态方法中是没有this关键字的

1. 静态方法中,只能访问静态,非静态是变化的,静态是不能访问非静态的,因为它不知道要访问的是哪一个对象的变量
2. 非静态方法可以访问所有
3. 静态方法没有this关键字,因为this指向的是对象,但是静态方法指向的确实这个类,


## 重新认识main方法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111558662.png)


## 继承

对象代表什么,就得封装对应的数据,并提供数据对应的行为

对于两种不同的类,但是具有很多共同的属性的时候我们就想着用继承,我们可以将共同的属性放置在一个类中,然后,只需要新建两个类,继承共有的类,然后单独写自己的属性特点

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111603634.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111605848.png)


### 继承类

java中提供了一个关键字extends,用这个关键字,我们可以让一个类和另一个类建立联系
```java
public class Student extends Person{}
```

其中Student称为子类(派生类),Person称为父类(基类或超类)

**使用继承的好处**

可以把多个子类中重复的代码抽取到父类中了,提高了代码的复用性
子类可以在父类的基础上,增加其他的功能,使得子类的功能更加完善

**当类与类之间,存在相同的内容,并满足子类是父类的一种,就可以考虑使用继承,来优化代码**

### 继承的特点

java只支持单继承,不支持多继承

一个子类只能继承一个父类,但支持多层继承

多层继承,子类A继承父类B,父类B可以继承父类C

虚拟及会自动为类添加继承对象Object
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111632591.png)

**Object自带的有方法**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111636970.png)


### 子类到底能继承父类的哪些内容

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122105242.png)

假设我们的构造方法能够继承的话，那么我们子类继承下来的构造方法就有可能和子类的类名不一致，因为这个传递下来的构造方法的名字是父类的名字

### 继承成员变量

非私有的变量能够直接继承，并且直接使用
私有的变量能够继承，但是不能直接使用，我们可以利用接口进行使用
**非私有变量**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122128799.png)

**私有变量**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122131625.png)


### 继承成员方法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122133536.png)


方法并不是一个一个继承的，而是我们在最高一级的类里面定义一个虚方法表，包括：
非private
非static
非final
只有父类的这三种对象才会继承
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122135927.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122139452.png)


### 继承中需要学的点

#### 继承中成员变量的访问特点
就近原则，谁离我近，我就用谁

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122156264.png)

super只能调用一个super，这个super就是类的父类

使用变量的时候，先到本类的成员变量找，然后在到父类的成员变量去找。

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122202409.png)

#### 成员方法的访问特点

直接调用的话就满足就近原则，谁里我近，我就用谁


#### 方法的重写
当父类的方法不能满足子类现在的需求了，我们就需要进行子类的重写

书写格式：
在继承体系中，子类中出现了和父类中一模一样的方法声明，我们就称子类的这个方法是重写的方法

@Override重写注释
1. @Override是放在重写后的方法上，校验子类重写时语法是否正确
2. 加入注解后如果有红色波浪线，表示语法错误
3. 建议重写方法都加@Override注解，代码安全，优雅
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304122209200.png)

**方法的重写就是覆盖父类传下来的虚方法表**

1. 重写方法的名称、形参列表必须与父类中的一致。
2. 子类重写父类方法时，访问权限子类必须大于等于父类（暂时了解︰空着不写<protected <public)，父类时public ，子类就不能时protect，private，但是子类的访问权限可以更高一点
3. 子类重写父类方法时，返回值类型子类必须小于等于父类，**这个一般是在说当父类返回类型是比较大的对象是比如Animal，那么子类可以是cat，dog，但是当父类是dog，cat类的时候子类不能是animal类**
4. 建议:重写的方法尽量和父类保持一致。
5. 只有被添加到虚方法表中的方法才能被重写

### 继承中的构造方法

子类的构造函数写的时候是利用这个super进行构造的，我们要注意，这个构造也可以用alt insert来进行快捷插入

父类的构造方法不会被子类继承
子类中所有的构造方法默认先访问父类中的无参构造，再执行自己。
**为什么**
1. 子类在初始化的时候，有可能会使用到父类中的数据，如果父类没有完成初始化，子类将无法使用父类的数据。
2. 子类初始化之前，一定要调用父类构造方法先完成父类数据空间的初始化。
**怎么调用父类构造方法的**
1. 子类构造方法的第一行语句默认都是: super()，不写也存在，**且必须在第一行**。
2. 如果想调用父类有参构造，必须手动写super进行调用。

**继承中构造方法的访问特点是什么?**
1. 子类不能继承父类的构造方法，但是可以通过super调用
2. 子类构造方法的第一行，有一个默认的super();
4. 默认先访问父类中无参的构造方法，再执行自己。
5. 如果想要方法文父类有参构造，必须手动书写。

### this、super使用总结

this：理解为一个变量，表示当前方法调用者的地址值：
他是一个局部变量，然后再方法调用的时候会产生值
**类似super（）**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132014343.png)


## 多态

让一个对象拥有不同的形态

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132125690.png)

多态的应用场景，比如你注册的时候，你可能注册为学生，老师，管理员，但是此时你往函数传递的类型是什么呢，此时你无论传递什么都不太合适，我们最好的是传递父类
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132215941.png)

什么是多态
1. 同类型的对象，表现出的不同形态
多态的表现形式
1. 父类类型 对象名称 = 子类对象；
多态的前提
1. 有继承关系
2. 有父类引用指向子类对象
3. 有方法重写
#### 多态方式创建对象
Fu f = new Zi（）；
>调用成员变量的时候，编译看左边，运行也看左边

再编译的时候会看左边的父类中有没有这个变量，如果有则编译成功，如果没有则编译失败。

> 调用成员方法的时候,编译看左边,运行看右边

我们再javac编译的时候我们先看父类中有没有这个变量,如果有则编译成功,如果没有则编译失败
但是再运行的时候调用的确实子类的方法,,因为这里面涉及到了方法的重写,父类的方法被再虚方法表中被覆盖掉了.

#### 多态的优势和弊端
>在多态形式下，右边对象可以实现解耦合，便于扩展和维护。

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132235402.png)

刚开始我们想让学术工作,但是后面几天我们想让老师去工作,这个时候我们就只需要改变这个student就行了

>定义方法的时候，使用父类型作为参数，可以接收所有子类对象，体现多态的扩展性与便利。

当我们向StringBuilder中添加数据的时候我们可以添加所有的对象类型,这就是因为这个obj是所有的对象的父类,满足多态的定义
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132237135.png)

我们定义集合的时候我们可以设置这个添加类型在尖括号里面,如果我们不写这个尖括号,那么我们就可以添加任意类型的数据

> 多态的优势

我们在调用方法的时候不能调用子类的特有功能,因为这样编译就通过不了.

**解决方案**

我们将这个父类类型转换为子类类型就可以了
```java
Animal a = new Dog();
a.lookhouse();//报错
Dog b = (Dog) a;//强制类型转换
```

转换的时候不能进行瞎转化,猫不能转换为狗,,所以我们在转换的时候要进行判断这个转换是不是合理的e
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132244355.png)

JDK14以后感觉这个写的太麻烦了,添加了一个新特性,可以将转化和判断写在一行
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304132245579.png)


# 包和final
包就是文件夹，用来管理各种不同功能的java类，方便后续管理
**包名的规则:公司域名反写＋包的作用，需要全部*英文小写*，见名知意。**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304160930915.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304160930543.png)

## 导包的规则

1. 使用同一个包中的类时，不需要导包。
2. 使用java.lang包中的类时，不需要导包。
3. 其他情况都需要导包
4. 如果同时使用两个包中的同名类，需要用全类名。

## final关键字

如果用final修饰方法，表示方法是最终方法，不能被重写
如果用final修饰类，表明该类是最终类，不能被继承
如果用final修饰变量， 叫做常量，只能被赋值一次

如果final修饰引用数据类型，记录的地址值不能发生改变，内部的属性值 还是可以发生改变的。
比如说，对象类型，数组类型

**字符串**
我们在学习字符串的时候知道字符串是不可以进行变化的，这也就是因为字符串的源代码中是final类型的。

## 常量

常量
实际开发中，常量一般作为系统的配置信息，方便维护，提高可读性。
**常量的命名规范:**
1. 单个单词:全部大写
2. 多个单词:全部大写，单词之间用下划线隔开
**细节:**
1. final修饰的变量是基本类型:那么变量存储的数据值不能发生改变。
2. final修饰的变量是引用类型:那么变量存储的地址值不能发生改变，对象内部的可以改变。

# 权限修饰符和代码块

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304161034210.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304161035045.png)


实际开发中，一般只用private和public
成员变量私有
●方法公开
特例:如果方法中的代码是抽取其他方法中共性代码，这个方法一般也私有


## 代码块

### 局部代码块
局部代码块，用大括号进行圈着，然后控制这个变量的内存占用时间，用完这个变量我们就回收，不占用多余空间。但是随着这个电脑的技术的发展，几个变量的定义对于内存那么大的电脑影响已经不大了。

### 构造代码块

就是你有两个构造方法，每次构造的时候都会输出一个东西，那么就可以把这个相同的输出语句提取出来，写成一个代码块，这个代码块先于构造语句的执行，这个代码块写在成员位置

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304161103927.png)

这个技术也渐渐的淘汰了，
这种方法太死了，不够灵活
我们可以通过新建一个方法来实现这个类似的功能

### 静态代码块

>格式
static{}

**特点**
需要通过static 关键字进行修饰，随着类的加载而加载，并且自动触发，只执行一次
**使用场景**
在类加载的时候，做一些数据初始化的时候使用
比如说我们在定义一个集合的时候，我们可以在集合中添加初始量。

> 这种方法和自己平时自己添加有什么区别呢

平时我们自己添加的时候是在方法里面进行添加的,只要是方法就有可能被重复调用,就有可能创建多个集合.

而用这个静态初始化就可以让这个初始化只执行了一次

# 抽象类

> 抽象类是必须要进行重写的,,不能够直接创建对象,我们可以采用多态的方法进行创建对象

对象代表什么,就得封装对应的数据,并提供相应的数据
当数据类型比较多的时候,我们就会用到继承,
当子类的某个行为大致方向相同,但是具体不同的话,我们一般是在父类中随便写一个,然后再子类中用多态进行重写

## 抽象类的定义格式
定义的时候我们就是直接再class前面加入abstract

## 抽象方法和抽象类

抽象方法:将共性的行为（方法）抽取到父类之后。
	由于每一个子类执行的内容是不一样，所以，在父类中不能确定具体的方法体。该方法就可以定义为抽象方法。
抽象类:如果一个类中存在抽象方法，那么该类就必须声明为抽象类

**注意事项**
1. 抽象类不能实例化,就是不能创建对象
2. 抽象类中不一定有抽象方法，有抽象方法的类一定是抽象类
3. 可以有构造方法,当创建子类对象的时候,给属性进行赋值
4. 抽象类的子类,写的时候会出现错误,我们可以alt加回车有两个选择
	1. 要么重写抽象类中的所有抽象方法
	2. 要么是抽象类

当父类的某个方法写什么都不太合适的时候我们这个时候就将其转化为抽象方法.
> 格式 修饰符 +abstract + 返回值类型 +函数名( ){ }

强制你这样命名,防止格式不规范

```java
package Abstract;  
public abstract class Animal {  
    private String name;  
    private int age;  
  
    public Animal() {  
    }  
  
    public Animal(String name, int age) {  
        this.name = name;  
        this.age = age;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public void setName(String name) {  
        this.name = name;  
    }  
  
    public int getAge() {  
        return age;  
    }  
  
    public void setAge(int age) {  
        this.age = age;  
    }  
    public void drink(){  
        System.out.print("喝水");  
    }  
    public abstract void eat();  
}
```



```java
package Abstract;  
  
public class Dog extends Animal{  
  
    public Dog() {  
    }  
  
    public Dog(String name, int age) {  
        super(name, age);  
    }  
  
    @Override  
    public void eat() {  
        System.out.println(getName()+"喝水");  
    }  
}
```

# 接口

 接口可以理解成一种规则
 接口时谁想用谁去对接

当我们需要给多个类但并不是全部的类定义规则的时候我们就要用到规则

## 接口与抽象类的异同

抽象类是用来表示一些事物
接口表示一些行为

## 如何定义一个接口
接口用关键字interface来定义
> public interface 接口名{ }

接口不能实例化
接口和类之间是实现关系，通过implements关键字表示
public class类名implements接口名
**接口中的方法都是抽象的方法**
接口的子类（实现类)
	要么重写接口中的所有抽象方法
	要么是抽象类

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201009472.png)



## 如何使用一个接口

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201024222.png)
## 接口中的成员有什么特点

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201025334.png)


## 接口和类的关系

- 类和类的关系
     继承关系，只能单继承，不能多继承，但是可以多层继承
- 类和接口的关系
     实现关系，可以单实现，也可以多实现，还可以在继承一个类的同时实现多个接口,但是要记得重写.
- 接口接口和接口的关系
	接口与接口之间也可以进行互相继承,可以单继承,也可以多继承

接口与接口之间的继承关系是用extends
```java
package connection_for_jiekou;  
  
public interface interface3 extends interface1,interface2{  
    public abstract void method3();  
}
```
之后我们如果想要调用这个接口三,我们就需要把这个接口三继承的两个父接口也要重写
```java
package connection_for_jiekou;  
  
public class method implements interface3{  
  
    @Override  
    public void method1() {  
          
    }  
  
    @Override  
    public void method2() {  
  
    }  
  
    @Override  
    public void method3() {  
  
    }  
}
```
当多个接口中有重名的方法,我们同时继承了多个接口,我们对这些重名的方法只需要重写一次就行了
**对于这些重名接口的调用,我们采用就近原则**

## JDK8开始接口中新增的方法
### default方法
JDK7以前:接口中只能定义抽象方法。
JDK8的新特性:接口中可以定义有方法体的方法。（默认、静态)
JDK9的新特性:接口中可以定义私有方法。

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201123238.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201123248.png)


**如果接口中新添加了一个新的规则,此时的子类规则要全部进行修改否则就会报错,这样的话不利于维护,怎么办呢**

如果接口中有方法体的方法就行了,这样就不需要子代规则重新写了.
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201210639.png)

### 静态static方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201215535.png)
**静态方法不能够进行重写**
**静态方法,只能通过接口名调用,不能通过实现类名或者对象名调用**

## JDK9以后新增的方法
JDK以前我们解决不同的方法的重复代码的方法,就是定义一个新的方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201219818.png)

但是你这个新定义的方法是个public类型的,我不想让其他人调用,只想让这两个特殊的函数进行调用,因此我们要改变这个方法的定义方式,将这个public改为private
**加入private是为了给默认方法服务的**
**加上private static是给静态方法服务的**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304201223298.png)



## 接口的应用
我们可以把多个类可能用到的方法都定义到接口里面
1. 接口代表规则，是行为的抽象。想要让哪个类拥有一个行为，就让这个类实现对应的接口就可以了。
2. 当一个方法的参数是接口时，可以传递接口所有实现类的对象，这种方式称之为接口多态。

## 适配器设计模式

**设计模式（Design pattern）是一套被反复使用、多数人知晓的、经过分类编目的、代码设计经验的总结。使用设计模式是为了可重用代码、让代码更容易被他人理解、保证代码可靠性、程序的重用性。**

**简单来说,设计模式就是各种套路**

如果我们接口中有10个方法,但是我们只想用其中一个,由于接口的规则,我们必须要进行所有方法的重写,这种方法很不方便

因此我们设计了一种方式,我们在套一层,这一层对所有的方法进行重写,然后我们在其他的类在进行使用这个接口中的方法时,我们只需要继承上一个类就行了.

当一个接口中抽象方法过多，但是我只要使用其中一部分的时候，就可以适配器设计模式
书写步骤:
1. 编写中间类XXXAdapter，实现对应的接口
2. 对接口中的抽象方法进行空实现
3. 让真正的实现类继承中间类，并重写需要用的方法
4. 为了避免其他类创建适配器类的对象，中间的适配器类用abstract进行修饰

此时因为继承了这个中间类,但是有可能我们的测试类还有其他的类,我们这个时候应该把这个测试类的父类,移动到这个中间类的父亲,然后再继承


# 内部类
## 什么是内部类
就是在一个类的里面,再定义一个类
举例就是再A类的内部定义B类,B类就被称为内部类
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304221609475.png)

类似结构体里面加入结构体,日期里面加入圣体类
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304221613515.png)

## 内部类的特点

>内部类的访问特点:

内部类可以直接访问外部类的成员，包括私有.
外部类要访问内部类的成员，必须创建对象

> 什么时候用到内部类

B类表示的事物是A的一部分,且B单独存在没有意义
比如,汽车的发动机,Arraylist的迭代器,人的心脏

## 成员内部类

写在成员位置的，属于外部类的成员。
成员内部类可以被一些修饰符所修饰，比如: private，默认,默认只能被本包的使用,protected,public，static等

在成员内部类里面，**JDK16之前不能定义静态变量**，JDK16开始才可以定义静态变量

### 获取成员内部类对象的两种方式

方式1： 外部类编写方法，对外提供内部类对象,一般是私有内部类才会这样用,其他情况下用方式2
方式2： 直接创建
格式： 外部类名.内部类名 对象名 = 外部类对象.内部类对象
范例： Outer.Inner oi = new Outer( ).new Inner;

如果内部类变量是私有的,我们在外界不能直接调用构建,我们可以在外部类里面定义一个接口,通过这个接口我们可以实现这个内部类
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304221923050.png)

默认的类型,我们可以在本包里面用,在其他包里面不能用

public 类型,在什么地方都能用

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304221949692.png)



内部类里面有一个隐藏的Outer this 变量,这个变量存放这个外部类的地址,如果只是用this的话,调用的是这个堆的内存,如果是outer this的话调用的就是这个外部类的信息.


## 静态内部类

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304221958455.png)

静态内部类只能访问外部类中的静态变量和静态方法

调用静态的方法,这个静态的方法不属于对象,虽然我们也可以通过对象进行调用,但是不推荐,我们可以通过外部类名.内部类名.方法名( );

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222002647.png)

## 局部内部类

1. 将内部类定义在方法里面就叫做局部内部类，类似于方法里面的局部变量。
1. 外界是无法直接使用，需要在方法内部创建对象并使用。
1. 该类可以直接访问外部类的成员，也可以访问方法内的局部变量。

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222006702.png)

## 匿名内部类

匿名内部类本质上就是隐藏了名字的内部类

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222017641.png)

匿名内部类就是我们用来实现接口的一种东西
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222127434.png)
后面的大括号包围的是一个内部类,这个内部类是没有名字,这个内部类实现了接口,或者是继承类
如果前面是接口那么就是实现接口,如果前面是类,那么就是实现类.
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222137776.png)

当我们有一个类只用一次的时候我们如果建立类的话太浪费了,我们可以采用匿名内部类的方法.

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222138535.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304222139308.png)


# 阶段项目实战

## 项目介绍和界面搭建

### 项目介绍
登录界面
1. 密码可以有一个显示密码和不显示密码的小按钮
2. 验证码可以每次点击刷新
注册按钮
1. 点击下去会发生变色
2. 当注册信息错误，比如说密码前后输入不一样就会有错误提示框
3. 还要做一个用户名的唯一性判断
游戏主界面
有标题，菜单，关于我们
1. 菜单里面可以切换图片，重新游戏，重新登录，关闭游戏，关于我们可以放置我们的练习方式
2. 还有统计游戏的步数
3. 按下A不松就能够显示最终效果，松开就能恢复原样
4. 按下W不松，我们就能直接一键通关
5. 我们可以根据名字来进行选择美女，哈哈可以恶搞朋友。

### 界面搭建

GUI是指采用图形化的方式显示操作界面
java中有两个包可以实现这个
AWT包和Swing包两个包里面可以实现GUI
**因为AWT包中是最先出来的，与现在的版本可能会出现一些兼容性的问题，所以我们现在最先用的GUI**

## 主界面分析

### 组件

JFrame 是最外层的窗体
JMenuBar最上层的菜单
JLabel管理文字和图片的容器，类似这个html的div
文字，图片，还有进度条等都是组件

### JFrame

```java
JFrame jFrame = new JFrame();  
jFrame.setSize(514,595);
```

这个JFrame就是这个创建一个窗口对象.
我们可以设置这个窗口的大小,但是这样的话,我们运行程序还是不能看到这个窗口,因为这个JDK中窗口是默认隐藏的,我们要通过
```java
jFrame.setVisible(true);
```
来实现这个界面的显示


JFrame是一个窗口类,我们通过这个窗口类来设置窗口,注册窗口单独写个类,登录窗口单独写一个类,游戏窗口单独写一个类,不同的类具有不同的游戏功能.
```java

设置界面的标题，settitle
设置界面置顶，setAlwaysOnTop
设置界面居中，查看JFrame文档，setLocationRelativeTo(c和null表示居中)
设置游戏的关闭方式，setDefaultCloseOperation
0 是什么都不做，1是默认的，2关闭所有的窗口才会停止运行，3是关闭一个窗口就停止运行

```

### JMenuBar，JMenu，JMenuItem

这三个层次是依次递进的
其中我们通过add来进行分类和选中
```java
JMenuBar jMenuBar = new JMenuBar();  
  
JMenu functionjMenu = new JMenu("功能");  
JMenu aboutjMenu = new JMenu("关于我们");  
  
JMenuItem replayItem = new JMenuItem("重新游戏");  
JMenuItem reLoginItem = new JMenuItem("重新登录");  
JMenuItem closeItem =  new JMenuItem("关闭游戏");  
  
JMenuItem accountItem = new JMenuItem("公众号");  
  
functionjMenu.add(replayItem);  
functionjMenu.add(reLoginItem);  
functionjMenu.add(closeItem);  
  
aboutjMenu.add(accountItem);  
  
jMenuBar.add(functionjMenu);  
jMenuBar.add(aboutjMenu);  
this.setJMenuBar(jMenuBar);
```


## 添加图片

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305041119331.png)

我们如果要自己设置位置的话,我们要自己去取消这个默认位置
setLayout(null)来清除这个默认位置

initImage
创建一个imageIcon的对象
创建imageLabel的对象

将图片放入imageLabel容器中，我们要设置这个容器的位置。用add
在放入容器前我们要指定位置，bounds来指定，指定位置之前我们要先清除这个默认位置。

然后我们一个一个的添加太麻烦了，我们可以将所有的路径放入一个字符集合里面，然后进行随机进行构建。
根据这个图片的位置规律我们进行添加图片

```java
private void initImage() {  
    int number = 1;  
    for (int i = 0; i < 4; i++) {  
        for (int j = 0; j < 4; j++) {  
            ImageIcon imageIcon = new ImageIcon("image/animal/animal1/"+number+".jpg");  
            JLabel jLabel = new JLabel(imageIcon);  
            jLabel.setBounds(105*j,105*i,105,105);  
            this.getContentPane().add(jLabel);  
            number++;  
        }  
    }  
}
```

## 打乱图片

将0-15放到数组里面，这个0-15顺序是被打乱的
将四个一组的打乱后的数据，放到这个二维数组里面
即本来一维数组是正常的排序,我们先将其打乱,然后我们在将其四个四个的放入这个二维数组中.
```java
int[] num = {1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16};  
for (int i = 0; i < num.length; i++) {  
    Random r = new Random();  
    int index = r.nextInt(num.length);  
    int temp = num[index];  
    num[index]=num[i];  
    num[i]=temp;  
}  
for (int i = 0; i < num.length; i++) {  
    System.out.print(num[i]+" ");  
}  
System.out.println();  
int[][] data = new int[4][4];  
int number = 0;  
for (int i = 0; i < 4; i++) {  
    for (int j = 0; j < 4; j++) {  
        data[i][j]=num[number];  
        number++;  
    }  
}  
for (int i = 0; i < 4; i++) {  
    for (int j = 0; j < 4; j++) {  
        System.out.print(data[i][j]+" ");  
    }  
    System.out.println();  
}
```

## 事件

我们被组件识别的操作,当我们对组件干了某件事情后,就会执行某段代码,我们可以通过鼠标点击,键盘的按,就会执行某个代码,
点击注册按钮,执行注册程序


**事件源**
按钮,图片,窗体

**事件,某些操作**
鼠标单击,鼠标划入

**绑定监听**
当事件源发生了某个实践,则执行某段代码
>KeyListener 键盘监听,比如说按tab键显示战绩

监听某个键位的点击

> MouseListener 鼠标监听

监听鼠标的按下,不松,抬起

> ActionListener 动作监听

这个是鼠标和键盘监听的精简版,只能监听鼠标点击,键盘的空格

### ActionListener
JButton job = new JButton();
创建一个按钮对象

1. 创建按钮对象
new的时候我们可以添加按钮的文字
2. 设置位置和宽高
setBounds
3. 添加动作监听
addActionListener（）里面的参数就是我们要执行的代码
4. 添加按钮
先调用这个隐藏容器getContentPane，然后我们在添加这个对象
本身这个ActionListener就是一个接口，我们通过重写这个接口来完成我们的功能，但是由于我们要重写的太多，我们不可能一个一个的去新建一个类，我们可以通过构造匿名内部类来进行重写,匿名内部类就是我们将这个重写的内容写在这个大括号里面
```java
jbt1.addActionListener(new ActionListener() {  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        System.out.println("宝贝你好");  
    }  
});```

另一种方法就是我们直接对这个类调用这个接口,然后再这个类李米娜进行重写函数,此时我们这里的addActionListener后面的参数是this

```java
package com_qiukehao_Puzzle_test;  
  
import javax.swing.*;  
import java.awt.event.ActionEvent;  
import java.awt.event.ActionListener;  
import java.util.Random;  
  
public class MyJFrame extends JFrame implements ActionListener {  
    JButton jbt1 = new JButton("小宝贝");  
    JButton jbt2 = new JButton("小老婆");  
    public MyJFrame(){  
        this.setSize(603, 680);  
        //设置界面的标题  
        this.setTitle("拼图单机版 v1.0");  
        //设置界面置顶  
        this.setAlwaysOnTop(true);  
        //设置界面居中  
        this.setLocationRelativeTo(null);  
        //设置关闭模式  
        this.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);  
        //取消默认的居中放置，只有取消了才会按照XY轴的形式添加组件  
        this.setLayout(null);  
  
        jbt1.setBounds(0,0,100,100);  
        jbt1.addActionListener(this);  
  
  
        jbt2.setBounds(200,200,100,100);  
        jbt2.addActionListener(this);  
        //将这两个按钮添加到这个界面中  
        this.getContentPane().add(jbt1);  
        this.getContentPane().add(jbt2);  
        this.setVisible(true);  
    }  
  
    @Override  
    public void actionPerformed(ActionEvent e) {  
        //对当前的按钮进行判断  
        //获取当前被操作的那个按钮对象  
        Object source = e.getSource();  
  
        if(source == jbt1){  
            jbt1.setSize(200,200);  
        }else if(source == jbt2){  
            Random r = new Random();  
            jbt2.setLocation(r.nextInt(500),r.nextInt(500));  
        }  
  
    }  
}
```


我们进行本类的重写，对这个类本身我们调用这个action的接口

### MouseListener
鼠标监听动作监听的东西更加复杂,包括鼠标的悬浮,鼠标点击,鼠标松开,鼠标的划出,四个动作,而Action Listener是只能监听鼠标的点击的

如果我们想要监听一个按钮的单击事件我们可以
- 动作监听
- 鼠标监听中的点击事件
- 鼠标监听中的鼠标松开事件

```java
//按下并释放  
@Override  
public void mouseClicked(MouseEvent e) {  
    System.out.println("你点我了");  
}  
//点下去,不松  
@Override  
public void mousePressed(MouseEvent e) {  
    System.out.println("按着不松");  
}  
//松开鼠标  
@Override  
public void mouseReleased(MouseEvent e) {  
    System.out.println("松开");  
}  
//划入  
@Override  
public void mouseEntered(MouseEvent e) {  
    System.out.println("划入");  
}  
//划出  
@Override  
public void mouseExited(MouseEvent e) {  
    System.out.println("划出");  
}
```

### KeyListener

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305051212674.png)

**键盘监听和别的还不太一样,前面的两种监听一般是给某些组件添加的,但是键盘监听一般是我们给整个界面添加监听事件的**

按下不松的方法会被虚拟机反复的调用
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305051217973.png)

```java
@Override  
public void keyTyped(KeyEvent e) {  
  
}  
  
@Override  
public void keyPressed(KeyEvent e) {  
    System.out.println("按下不松");  
}  
  
@Override  
public void keyReleased(KeyEvent e) {  
    System.out.println("松开按键");  
}
```

#### 区分按键

我们用e.getKyeCode( )方法来获取这个按键,这个的发布值是int类型,我们可以对其进行强制转化为char型就可以观察到我们按的是什么键盘了

```java
@Override  
public void keyPressed(KeyEvent e) {  
    System.out.println("按下不松");  
    char c = (char) e.getKeyCode();  
    System.out.println(c);  
}
```

## 美化界面

1. 给每一个图片添加一个边框，给图片添加背景
2. 让图片进行居中显示

我们给每一个图片添加一个偏移量，在seBounds里面添加一个偏移量就可以让所有图片都进行偏移了

### 添加背景图片
我们添加背景的时候我们记住
**先添加的图片在图层上方，后添加的在图层下方**

```java
ImageIcon bg = new ImageIcon("image/background.png");  
JLabel background = new JLabel(bg);  
background.setBounds(40,40,508,560);  
this.getContentPane().add(background);       //获取隐藏容器
```

### 添加边框

```java
jLabel.setBorder(new BevelBorder(1));
```

0是让边框有凸起来,1是凹下去了

其中BevelBorder是边框类型,我们可以通过参考文档我们来实现各种各样的边框

为了防止我们记错这个1,和0,我们可以通过这个BevelBorder.来调用这个接口里面自己定义的常量,RAISE表示0凸起,LOWERED表示1凹下去

```java
jLabel.setBorder(new BevelBorder(BevelBorder.LOWERED));
```

## 移动图片
上移动
向上移动实际上就是把空白方块下方的图片上移

我们是先调整图片的位置，然后再同意初始化所有的图片

**注意点是**
1. 我们这个是要找准0，这个0在哪和你的数组有关系，刚开始我的数组是1-16，这样的话，就是0就是16，我们不仅要靠这个0来进行移动，我们获取初始的x和y的时候我们还要利用这个0获得
2. 第二个注意点是我们进行操作后，图片是不能产生效果的，我们必须要清除缓存，然后再初始化，最后再刷新才能实现这个操作效果 
```java
this.getContentPane().removeAll();//清除内容
this.getContentPane().repaint(); // 刷新界面
```


```java
public void keyReleased(KeyEvent e) {  
    //获取元素  
    //左 37，上38 右39，下40  
    int code = e.getKeyCode();  
    if(code==37){  
        //将位置0的元素与右边的元素交换  
        System.out.println("左移了");  
        changeSiteLeft();  
    }else if(code==38){  
        //上移就是将0下面的位置与0交换  
        System.out.println("上移了");  
        changeSiteUp();  
    } else if (code==39) {  
        //右移就是将0左边的位置与0交换  
        System.out.println("右移了");  
        changeSiteRight();  
    } else if (code==40) {  
        //将0上边的元素与0交换  
        System.out.println("下移了");  
        changeSiteDown();  
    }  
}
```

```java
private void changeSiteLeft(){  
    data[x][y]=data[x][y+1];  
    data[x][y+1]=0;  
    y++;  
    initImage();  
}  
private void changeSiteRight(){  
    data[x][y]=data[x][y-1];  
    data[x][y-1]=0;  
    y--;  
    initImage();  
}  
private void changeSiteUp(){  
    data[x][y]=data[x+1][y];  
    data[x+1][y]=0;  
    x++;  
    initImage();  
}  
private void changeSiteDown(){  
    data[x][y]=data[x-1][y];  
    data[x-1][y]=0;  
    x--;  
    initImage();  
}
```

同时注意我们要加入一个判断，防止这个移动的时候这个产生越界

## 一键查询完整图片
查询完整图片就是我们将这个页面用完整土拍你覆盖就行了，记得清除页面组件和刷新页面内容
```java
@Override  
public void keyPressed(KeyEvent e) {  
    //我们利用这个快捷键，查看完整图片  
    int code =e.getKeyCode();  
    if(code==65){  
        System.out.println("按下了a");  
        //清除所有的数据，放入自己完整的图片，然后在刷新，  
        this.getContentPane().removeAll();  
        ImageIcon all = new ImageIcon("image/animal/animal1/all.jpg");  
        JLabel jLabel = new JLabel(all);  
        jLabel.setBounds(105,105,420,420);  
        this.getContentPane().add(jLabel);  
        //添加背景  
        ImageIcon bg = new ImageIcon("image/background.png");  
        JLabel background = new JLabel(bg);  
        background.setBounds(40,40,508,560);  
        this.getContentPane().add(background);       //获取隐藏容器  
        this.getContentPane().repaint(); // 刷新界面  
    }  
}
```

## 一键通关

```java
private void cheatImage(){  
    int[][] num = {{1,2,3,4},{5,6,7,8},{9,10,11,12},{13,14,15,0}};  
    this.getContentPane().removeAll();  
    for (int i = 0; i < 4; i++) {  
        for (int j = 0; j < 4; j++) {  
            ImageIcon imageIcon = new ImageIcon("image/animal/animal1/"+num[i][j]+".jpg");  
            JLabel jLabel = new JLabel(imageIcon);  
            jLabel.setBounds(105*j+83,105*i+134,105,105);  
            jLabel.setBorder(new BevelBorder(BevelBorder.LOWERED));  
            this.getContentPane().add(jLabel);  
        }  
    }  
    ImageIcon bg = new ImageIcon("image/background.png");  
    JLabel background = new JLabel(bg);  
    background.setBounds(40,40,508,560);  
    this.getContentPane().add(background);       //获取隐藏容器  
    this.getContentPane().repaint(); // 刷新界面  
}
```

## 判断胜利
我们判断胜利,只需要比较两个数组的是否相同即可

```java
//如果胜利了，直接结束方法  
if(judgeWin()){  
    return;  
}
```


```java
public boolean judgeWin(){  
    int[][] num = {{1,2,3,4},{5,6,7,8},{9,10,11,12},{13,14,15,0}};  
    for (int i = 0; i < data.length; i++) {  
        for (int j = 0; j <num.length; j++) {  
            if(num[i][j]!=data[i][j]){  
                return false;  
            }  
        }  
    }  
    System.out.println("胜利");  
    return true;  
    //如果到这里都没退出说明，这个程序是正确的，我们此时要添加这个胜利图标  
  
}
```

## 优化代码
这个一键通关，我们一看就是和initImage重复的，我们要想的是怎么利用这个重复代码，而不是直接想着去重写代码

## 统计步数
这个本身也是一个组件,我们确定好位置就行了
```java
JLabel stepCount = new JLabel("步数: "+count);  
stepCount.setBounds(50,30,100,20);  
this.getContentPane().add(stepCount);
```
我们count++的时候，我们要写在各个函数内部，否则的话当越界的时候也可能被统计到

## 重新游戏 
1. 我们要给重新游戏绑定点击事件,这个点击事件是我们的ActionListener,我们通过接口进行调用.
2. 然后打乱二维数组中的数字
3. 加载图片
4. 计步器清零

```java
data=getData();  
count=0;  
initImage();
```

## 重新登录

```java
this.setVisible(false);  
new LoginJFrame();
```

## 关闭游戏
```java
System.exit(0);
```

## 关于我们
```java
JDialog j = new JDialog();  
JLabel about = new JLabel(new ImageIcon("image/qiu.png"));  
about.setBounds(0,0,359,359);  
j.getContentPane().add(about);  //  
j.setSize(360,360);  //设置宽高  
j.setAlwaysOnTop(true);  //始终置顶  
j.setLocationRelativeTo(null);  //居中  
j.setModal(true);   //弹框不关闭无法进行别的操作  
j.setVisible(true);  //让弹框显示出来
```

##  打包

1. 一定要包含图形化界面
2. 代码要打包起来
3. 游戏用到的图片也要打包起来
4. JDK也要打包

1. 将所有的代码打包成一个压缩包,jar后缀的压缩包
2. 把jat包转换成exe安装包
3. 把第二步的exe,图片,jdk整合在一起,变成最终的exe安装包

我打包了这个项目，项目的jar包23kb，然后jdk是150多mb，最后的大小是160多mb

## 另外
按照黑马阿伟老师给的参考文档直接打包就好了，整个打包过程不难，获取方式是关注黑马程序员公众号，领取资料，领取java资料，在day18-API文件夹里有这个文档。如果不想自己麻烦的话，可以下载我上传的，但是这里只能上传文档，具体需要的软件exe4j还有innosetup都是没有的。还是推荐关注公众号，能够获取到好多编程资源。



# 常见的API

## Math

从JDK版本1开始的,用来计算的一些方法
这里面定义了两个常量的PI 和E这两个是最接近pi的值和最接近对数的值

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181026116.png)


1. abs(int a ) 取绝对值
2. ceil(double a)向上取整
3. floor(double a )向下取整
4. round(float a)四舍五入
5. max(int a,int b) 取最大值
6. pow (double a,double b) a的b次幂
7. random() 返回值为double的随机数,范围是[ 0.0 , 1.0 );  ]

### abs
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181028086.png)
这属于一个小bug
当我们的数据比较大的时候,我们可以用Math,absExact来进行使用,这个并不能纠错,但是可以提示我们错误,原来的是不提示错误直接输出了.

### ceil

相当于数学的进一法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181030528.png)

### floor
与ceil相反,相当于数学中的退一法

### round
四舍五入
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181032522.png)

### 开平方sqrt,开立方根cbrt
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181034531.png)


### 数学水题

#### 质数的优化

```java
public class 质数优化 {  
    public static void main(String[] args) {  
        int i;  
        int j;  
        Scanner input = new Scanner(System.in);  
        System.out.println("请输入你要判断的数");  
        int num = input.nextInt();  
        for(i=2;i<Math.sqrt(num);i++){  
            for(j= (int) Math.sqrt(num); j<num; j++){  
                if(i*j==num){  
                    System.out.println("不是质数，因子为："+i+"*"+j);  
                    break;  
                }  
            }  
        }  
    }  
}
```


## System
我们通过这个System名直接调用
### exit
0,表示当前虚拟机是正常停止
非0,表示当前虚拟机是非正常停止

### currentTimeMills

计算机的时间原点
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181057088.png)

由于时区的影响,我们获取的时间原点是
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/20230518105749.png)
1s=1000ms
1ms=1000us
1us=1000ns

```java
public static long currentTimeMills();//返回当前系统的时间毫秒值形式
```

我们通过这个代码可以获得这个程序执行所需的总时间
### arraycopy

```java
int [] arr1 = {1,2,3,4,5,6};
int [] arr2 = new int[6];
System.arraycopy(arr1,0,arr2,0,6);
```

把arr1数组中的数据拷贝到arr2中
1. 参数一:数据源，要拷贝的数据从哪个数组而来
2. 参数二:从数据源数组中的第几个索引开始拷贝
3. 参数三:目的地，我要把数据拷贝到哪个数组中
4. 参数四:目的地数组的索引。
5. 参数五:拷贝的个数

```java
int [] arr1 = {1,2,3,4,5,6,7,8,9,10};
int [] arr2 = new int[10];
System.arraycopy(arr1,0,arr2,4,3);
//0 0 0 0 1 2 3 0 0 0
```

#### 注意点
1. 如果这个 拷贝的数组都是基本数据类型,那么两者的数据类型必须一模一样,否则就会报错
2. 在拷贝的时候数组不能越界
3. 如果数据源数组和目的地数组都是引用数据类型，那么子类类型可以赋值给父类类型,比如说Student类型可以赋值给Person类型

## Runtime

### getRuntime()
当前系统的虚拟机环境
因为runtime对象的构造函数时私有的,我们不能直接new,所以我们要用这个getRuntime
>Runtime r1 = Runtime.getRuntime()
### exit()
停止虚拟机
> Runtime.getRuntim().exit(0)
### availableProcessors
获得cpu的线程数
>sout(Runtime.getRuntime().availableProcessors());

### maxMemory
JVM能从系统中获得的总内存大小

### totalMemory
JVM已经从系统中获取总内存大小


### freeMemory
JVM剩余内存大小


### exec
运行cmd命令

我们可以添加这个cmd关机指令恶搞朋友

Runtime.getiRuntime().exec("shutdowm -s -t 时间")关机按钮
Runtime.getiRuntime().exec("shutdowm -a") 停止关机


## Object

Object是java中的顶级父类，所有的类都直接或间接的继承于Object类

Object只有一个空参构造，我们通过空参构造进行创建对象

我们自己新建一个类，它默认继承这个object类的

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191502132.png)

### toString
Object.toString() 返回的是一个字符串---包名加类名,加地址值

当我们打印一个对象的时候,底层会调用,对象的toString方法,把对象变成字符串.


### equals
我们查看这个方法的源代码发现这个是通过this== object来进行比较的,这种比较是比较的两个对象的地址,但是大多数情况下我们是比较的对象里面的内容,因此我们在这种情况下我们一般选择进行重写

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191454724.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191501801.png)


### clone

#### 浅克隆
浅克隆是将A对象的属性值,玩去哪拷贝给B对象,也叫对象拷贝,对象复制,对象的变量属性地址是相同的
#### 深克隆
深克隆对于基本数据类型也是拷贝地址,但是对于引用数据类型,就是新建一个空间,然后进行存放数据的,两者之间的地址内容是不相同 的
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191513598.png)

父类的clone是默认浅克隆,如果我们想实现这个深克隆,我们要自己进行重写.

由于对象的数据类型不是确定的,一维数组有一维数组的写法,二维数组有二维数组的写法,为了方便我们进行编程,我们通过第三方的工具可以实现这个重写功能;

##### 第三方工具的代码
1. 我们会现在这个项目中新建一个文件夹lib,然后将别人写的jar包给复制进来
2. 然后我们将这个jar包右击添加到library,

```java
//第三方的工具1.第三方写的代码导入到项目中
//2.编写代码
Gson gson = new Gson( );//把对象变成一个字符串
string s = gson.to]son(u1);//再把字符串变回对象就可以了
User user = gson.fromJson(s, User.class);//打印对象
system.out.println(user);

```



## Objects

在java中我们不能用字符null来调用方法否则这个系统会报错
Objects类所在包是在java.util包下，因此在使用的时候需要进行导包。并且Objects类是被final修饰的，因此该类不能被继承。

暂时先不了解，等用到自己在查阅参考文档

## BigInteger类
### 引入

java整数中只有四种类型,byte,short,int,long
其中分别是1,2,4,8个字节数

平时在存储整数的时候，Java中默认是int类型，int类型有取值范围：-2147483648 ~ 2147483647。如果数字过大，我们可以使用long类型，但是如果long类型也表示不下怎么办呢？ 

就需要用到BigInteger，可以理解为：大的整数。                                                                           

有多大呢？理论上最大到42亿的21亿次方                                                                                  
基本上在内存撑爆之前，都无法达到这个上限。                                                                               

### 概述
BigInteger所在包是在java.math包下，因此在使用的时候就需要进行导包。我们可以使用BigInteger类进行大整数的计算

对象一旦创建,内部的对象值是不能修改的
### 构造方法


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191628018.png)


```java
public BigInteger(int num, Random rnd) 		//获取随机大整数，范围：[0 ~ 2的num次方-1]
public BigInteger(String val) 				//获取指定的大整数
public BigInteger(String val, int radix) 	//获取指定进制的大整数
    
下面这个不是构造，而是一个静态方法获取BigInteger对象
public static BigInteger valueOf(long val) 	//静态方法获取BigInteger的对象，内部有优化
```

```java
BigInteger test = new BigInteger(4,new Random());
```

这种构造方法构造的不是一个确定的整数,而是一个随即数

```java
BigInteger test1 = new BigInteger("99999999999999999999999");
```

这种构造方法可以构造指定大小的数字,引号必须是整数,

```java
BigInteger test3 = new BigInteger("100",2);
```

可以构建指定进制的数字,引号里面的数字必须符合进制

```java
BigInteger test4 = BigInteger.valueOf(9999999999999999999999999);
```

创建静态对象,但是这个静态对象的范围比较小,我们一般不用


### 常见成员方法

```java
public BigInteger add(BigInteger val)					//加法
public BigInteger subtract(BigInteger val)				//减法
public BigInteger multiply(BigInteger val)				//乘法
public BigInteger divide(BigInteger val)				//除法
public BigInteger[] divideAndRemainder(BigInteger val)	 //除法，获取商和余数
public  boolean equals(Object x) 					    //比较是否相同
public  BigInteger pow(int exponent) 					//次幂、次方
public  BigInteger max/min(BigInteger val) 				//返回较大值/较小值
public  int intValue(BigInteger val) 					//转为int类型整数，超出范围数据有误
```

BigInterget对象的值是不能进行修改的,而是我们产生了一个新的BigInterger对象的值

```java
//5.对象一旦创建内部的数据不能发生改变
BigInteger bd9 =BigInteger.valueOf(1);
BigInteger bd10 =BigInteger.valueOf(2);
//此时，不会修改参与计算的BigInteger对象中的借，而是产生了一个新的BigInteger对象记录
BigInteger result=bd9.add(bd10);
System.out.println(result);//3
```


## BigDecimal类

### 引入概论
首先我们来分析一下如下程序的执行结果

```java
public class BigDecimalDemo01 {

    public static void main(String[] args) {
        System.out.println(0.09 + 0.01);
        //0.09999999999999999
    }

}
```

这样的结果其实就是一个丢失精度的结果。为什么会产生精度丢失呢？

在使用float或者double类型的数据在进行数学运算的时候，很有可能会产生精度丢失问题。我们都知道计算机底层在进行运算的时候，使用的都是二进制数据； 当我们在程序中写了一个十进制数据 ，在

进行运算的时候，计算机会将这个十进制数据转换成二进制数据，然后再进行运算，计算完毕以后计算机会把运算的结果再转换成十进制数据给我们展示； 如果我们使用的是整数类型的数据进行计算，那

么在把十进制数据转换成二进制数据的时候不会存在精度问题； 如果我们的数据是一个浮点类型的数据，有的时候计算机并不会将这个数据完全转换成一个二进制数据，而是将这个将其转换成一个无限的

趋近于这个十进数的二进制数据； 这样使用一个不太准确的数据进行运算的时候， 最终就会造成精度丢失；为了提高精度，Java就给我们提供了BigDecimal供我们进行数据运算。

### 常见的构造方法

![1576134383441.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191719099.png)


# 正则表达式

## 1.1 正则表达式的概念及演示

- 在Java中，我们经常需要验证一些字符串，例如：年龄必须是2位的数字、用户名必须是8位长度而且只能包含大小写字母、数字等。正则表达式就是用来验证各种字符串的规则。它内部描述了一些规则，我们可以验证用户输入的字符串是否匹配这个规则。
- 先看一个不使用正则表达式验证的例子：下面的程序让用户输入一个QQ号码，我们要验证：
  - QQ号码必须是5--15位长度
  - 而且必须全部是数字
  - 而且首位不能为0

```java
package com.itheima.a08regexdemo;

public class RegexDemo1 {
    public static void main(String[] args) {
        /* 假如现在要求校验一个qq号码是否正确。
            规则:6位及20位之内，日不能在开头，必须全部是数字。
            先使用目前所学知识完成校验需求然后体验一下正则表达式检验。
        */

        String qq ="1234567890";
        System.out.println(checkQQ(qq));

        System.out.println(qq.matches("[1-9]\\d{5,19}"));

    }

    public static boolean checkQQ(String qq) {
        //规则:6位及20位之内，日不能在开头，必须全部是数字 。
        //核心思想:
        //先把异常数据进行过滤
        //下面的就是满足要求的数据了。
        int len = qq.length();
        if (len < 6 || len > 20) {
            return false;
        }
        //0不能在开头
        if (qq.startsWith("0")) {
            return false;
        }
        //必须全部是数字
        for (int i = 0; i < qq.length(); i++) {
            char c = qq.charAt(i);
            if (c < '0' | c > '9') {
                return false;
            }
        }
        return true;
    }
}
```

- 使用正则表达式验证：

```java
public class Demo {
    public static void main(String[] args) {
        String qq ="1234567890";
        System.out.println(qq.matches("[1-9]\\d{5,19}"));
    }
}
```

**我们接下来就重点学习怎样写正则表达式**

## 正则表达式字符类



- 语法示例：

> \[abc\]：代表a或者b，或者c字符中的一个。
	**一次只能匹配一个字符,如果正则表达式少于字符串的长度,那么就会返回false,如果我们想要让他们多匹配,我们就要多添加几个正则表达式**
```java
        System.out.println("a".matches("[abc]")); // true
        System.out.println("z".matches("[abc]")); // false
		System.out.println("ab".matches("[abc]")); // false
		System.out.println("ab".matches("[abc][abc]")); // true
```

> \[^abc\]：代表除a,b,c以外的任何字符。

```java
        System.out.println("a".matches("[^abc]")); // false
        System.out.println("z".matches("[^abc]")); // true
        System.out.println("zz".matches("[^abc]")); //false
        System.out.println("zz".matches("[^abc][^abc]")); //true
```

>[a-z]：代表a-z的所有小写字符中的一个, 
>[A-Z]：代表A-Z的所有大写字符中的一个。
   [a-zA-Z0-9]代表a-z或者A-Z或者0-9之间的任意一个字符。
   [0-9]：代表0-9之间的某一个数字字符。
   [a-dm-p]：a 到 d 或 m 到 p之间的任意一个字符。 

```java
        // a到zA到Z(包括头尾的范围)
        System.out.println("a".matches("[a-zA-z]")); // true
        System.out.println("z".matches("[a-zA-z]")); // true
        System.out.println("aa".matches("[a-zA-z]"));//false
        System.out.println("zz".matches("[a-zA-Z]")); //false
        System.out.println("zz".matches("[a-zA-Z][a-zA-Z]")); //true
        System.out.println("0".matches("[a-zA-Z]"));//false
        System.out.println("0".matches("[a-zA-Z0-9]"));//true
```


```java
        System.out.println("a".matches("[a-d[m-p]]"));//true
        System.out.println("d".matches("[a-d[m-p]]")); //true
        System.out.println("m".matches("[a-d[m-p]]")); //true
        System.out.println("p".matches("[a-d[m-p]]")); //true
        System.out.println("e".matches("[a-d[m-p]]")); //false
        System.out.println("0".matches("[a-d[m-p]]")); //false
```



> 且

```java
        // [a-z&&[def]] a-z和def的交集。为:d，e，f
        System.out.println("a".matches("[a-z&[def]]")); //false 此时的且简简单单的表示一个符号而已
        System.out.println("&".matches("[a-z&[def]]")); //true 此时的且简简单单的表示一个符号而已
        System.out.println("d".matches("[a-z&&[def]]")); //true  这里的且才是表示且符号
        System.out.println("0".matches("[a-z&&[def]]")); //false
```

总结规律,这个正则表达式这个双引号不能少,范围的话要用括号来代替,,其中这几个联立范围的正则表达式的顺序没有要求
这个或者可以用括号,也可以不用括号,但最好用括号


## 正则表达式预定义字符

1. "." ： 匹配任何字符。
2. "\\d"：任何数字[0-9]的简写；
3. "\\D"：任何非数字\[^0-9\]的简写；
4. "\\s"： 空白字符：[ \\t\\n\\x0B\\f\\r] 的简写
5. "\\S"： 非空白字符：\[^\s\] 的简写
6. "\\w"：单词字符：[a-zA-Z_0-9]的简写
7. "\\W"：非单词字符：\[^\w\]

转义字符\\能够让在java中原本有意义的字符变成没有意义,普普通通的字符
我们要始终记得,这个转义字符\\也是一个字符,为了让这个字符表示出来,我们一般要在这个转义字符\\前面再加入一个\\,因此这个\\不单独出现



## 正则表达式数量词

语法示例：

1. X? : 0次或1次
2. X* : 0次到多次
3. X+ : 1次或多次
4. X{n} : 恰好n次
5. X{n,} : 至少n次
6. X{n,m}: n到m次(n和m都是包含的)


正则表达式是Paten类里面的
## 特点


小括号表示分组,表示这一组数据然后就可以对这一组进行量词的修饰
```java
String regex3 = "\\w+@[\\w&&[^_]]{2,6}(\\.[a-zA-Z]{2,3}){1,2}";
```

"|"表示两组数组取一组就行了

```java
String regex4 = "([01]\\d|2[0-3]):[0-5]\\d:[0-5]\\d";
```

忽略大小写

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307151245355.png)


组合字符用小括号进行分组
```java
String regexSimple ="\\d{17}(\\d|X|x)";
```

一步一步的找规律,然后进行拼接就好了
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307151252483.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307151254555.png)


## 爬虫

Pattern：表示正则表达式
Matcher：文本匹配器，作用按照正则表达式的规则去读取字符串，从头开始读取。在大串中去找符合匹配规则的子串。

```java
package com.itheima.a08regexdemo;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexDemo6 {
    public static void main(String[] args) {
        String str = "Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，" +"因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";
        //1.获取正则表达式的对象,这个对象表示的是这个正则表达式的规则
        Pattern p = Pattern.compile("Java\\d{0,2}");
        //2.获取文本匹配器的对象
        //拿着m去读取str，找符合p规则的子串
        Matcher m = p.matcher(str);
		
        //3.利用循环获取 这个find函数判断是否找到了对象,如果找到了就返回true,否则返回false
        while (m.find()) {
	        //获取这个找到的这个对象的下标,并截取这一段的内容,
            String s = m.group();
            System.out.println(s);
        }


    }

    private static void method1(String str) {

        //获取正则表达式的对象
        Pattern p = Pattern.compile("Java\\d{0,2}");
        //获取文本匹配器的对象
        //m:文本匹配器的对象
        //str:大串
        //p:规则
        //m要在str中找符合p规则的小串
        Matcher m = p.matcher(str);

        //拿着文本匹配器从头开始读取，寻找是否有满足规则的子串
        //如果没有，方法返回false
        //如果有，返回true。在底层记录子串的起始索引和结束索引+1
        // 0,4
        boolean b = m.find();

        //方法底层会根据find方法记录的索引进行字符串的截取
        // substring(起始索引，结束索引);包头不包尾
        // (0,4)但是不包含4索引
        // 会把截取的小串进行返回。
        String s1 = m.group();
        System.out.println(s1);


        //第二次在调用find的时候，会继续读取后面的内容
        //读取到第二个满足要求的子串，方法会继续返回true
        //并把第二个子串的起始索引和结束索引+1，进行记录
        b = m.find();

        //第二次调用group方法的时候，会根据find方法记录的索引再次截取子串
        String s2 = m.group();
        System.out.println(s2);
    }
}
```


## 按照要求进行爬取数据

## 按要求爬取

需求：
​	有如下文本，按要求爬取数据。   
​	 Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台。
需求1：
​	爬取版本号为8，11.17的Java文本，但是只要Java，不显示版本号。
需求2：
​	爬取版本号为8，11，17的Java文本。正确爬取结果为：Java8 Java11 Java17 Java17
需求3：
​	爬取除了版本号为8，11，17的Java文本。

>忽略大小写

(?i)Java

> 查找某个数据,但是只获取这个数据的前面部分

((?i)java)(?=8|11||17)

        //1.定义正则表达式
        //?理解为前面的数据Java
        //=表示在Java后面要跟随的数据
        //但是在获取的时候，只获取前半部分

> 除了某一项

?!...

代码示例：

```java
public class RegexDemo9 {
    public static void main(String[] args) {
        /*
            有如下文本，按要求爬取数据。
                Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，
                因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台


            需求1:爬取版本号为8，11.17的Java文本，但是只要Java，不显示版本号。
            需求2:爬取版本号为8，11，17的Java文本。正确爬取结果为:Java8 Java11 Java17 Java17
            需求3:爬取除了版本号为8，11.17的Java文本，
        */
        String s = "Java自从95年问世以来，经历了很多版本，目前企业中用的最多的是Java8和Java11，" +
            "因为这两个是长期支持版本，下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";

        //1.定义正则表达式
        //?理解为前面的数据Java
        //=表示在Java后面要跟随的数据
        //但是在获取的时候，只获取前半部分
        //需求1:
        String regex1 = "((?i)Java)(?=8|11|17)";
        //需求2:
        String regex2 = "((?i)Java)(8|11|17)";
        String regex3 = "((?i)Java)(?:8|11|17)";
        //需求3:
        String regex4 = "((?i)Java)(?!8|11|17)";

        Pattern p = Pattern.compile(regex4);
        Matcher m = p.matcher(s);
        while (m.find()) {
            System.out.println(m.group());
        }
    }
}

```

## 贪婪爬取和非贪婪爬取

尽可能多X+
尽可能少X+?
```markdown
            只写+和*表示贪婪匹配

            +? 贪婪匹配
            *? 非贪婪匹配

            贪婪爬取:在爬取数据的时候尽可能的多获取数据
            非贪婪爬取:在爬取数据的时候尽可能的少获取数据

            ab+:
            贪婪爬取:abbbbbbbbbbbb
            非贪婪爬取:ab
```

## 1.13 String的split方法中使用正则表达式

- String类的split()方法原型：

  ```java
  public String[] split(String regex)
  //参数regex表示正则表达式。可以将当前字符串中匹配regex正则表达式的符号作为"分隔符"来切割字符串。
  ```

- 代码示例：

```java
/*
            有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
            要求1:把字符串中三个姓名之间的字母替换为vs
            要求2:把字符串中的三个姓名切割出来*/

String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";
//细节:
//方法在底层跟之前一样也会创建文本解析器的对象
//然后从头开始去读取字符串中的内容，只要有满足的，那么就切割。
String[] arr = s.split("[\\w&&[^_]]+");
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

## 1.14 String类的replaceAll方法中使用正则表达式

- String类的replaceAll()方法原型：

```java
public String replaceAll(String regex,String newStr)
//参数regex表示一个正则表达式。可以将当前字符串中匹配regex正则表达式的字符串替换为newStr。
```

- 代码示例：

```java
/*
            有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
            要求1:把字符串中三个姓名之间的字母替换为vs
            要求2:把字符串中的三个姓名切割出来*/

String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";
//细节:
//方法在底层跟之前一样也会创建文本解析器的对象
//然后从头开始去读取字符串中的内容，只要有满足的，那么就用第一个参数去替换。
String result1 = s.replaceAll("[\\w&&[^_]]+", "vs");
System.out.println(result1);
```


## 分组
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307152243786.png)


## 练习(捕获分组)

### 捕获分组
后续还要继续使用本组的数据,正则内部使用\\加组号
正则外部使用:$组号

### 非捕获分组
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307152322202.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307160008714.png)


### 分组

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307152319315.png)


```java
package demo.day1;

import java.util.Scanner;

public class 分组练习 {
    public static void main(String[] args) {
        Scanner    sc = new Scanner(System.in);
        String str = sc.next();
        //判断一个字符串的开始字符和结束字符是否一致,只考虑一个字符
        String regex1 ="(.).+\\1";
        //判断一个字符串的开始部分和结束部分是否一直,可以有多个字符
        System.out.println(str.matches(regex1));
        String regex2="(.+).+\\1";
        System.out.println(str.matches(regex2));
        String regex3="((.)\\2*).+\\1";
        System.out.println(str.matches(regex3));
        sc.close();
    } 
}

```

### 替换

$1表示替换第一组的内容
```java
    public static void main(String[] args) {
        //Scanner input = new Scanner(System.in);
        //String str = input.next();
        //正则表达式进行替换
        //我要学学编编编编程程程程程程
        String str ="我要学学编编编编程程程程程程";
        // String regex ="(.)\\1+";
        String result = str.replaceAll("(.)\\1+", "$1");
        System.out.println(result);
        //input.close();
    }
```


# date类

date的定义,
date的gettime方法
date的settime方法
注意使用date的时候导包一定要导入utils包下面的,否则就会无法正确识别了
```java
    public static void main(String[] args) {
        //导包一定要导入java.utils包下的,千万不要导错
        Date date1 = new Date();
        System.out.println(date1);
        Date date = new Date(0L);
        System.out.println(date);
        date.setTime(1000L);
        System.out.println(date);
        //打印开始节点之后的一年的实践
        long time = date.getTime();
        time +=  1000L*60*60*24*365;
        date.setTime(time);
        System.out.println(date);
    }
```


## SimpleDateFormat类

作用是:
格式化,将时间变成我们喜欢的格式
将字符串表示的对象转换为Date格式

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162002972.png)

对应这个格式进行添加来进行修改就可以了
```java
SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy年MM月dd日 第DD天第ww周 一个月的第WW周 E HH时mm分ss秒");
2023年07月16日 第197天第29周 一个月的第04周 周日 20时35分55秒
```


## Calendar

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162109972.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162114235.png)


要注意这个外国的日期和周几和中国的不太一样,不太符合我们的观感

```java
package demo.day2;

import java.util.Calendar;
import java.util.Date;

public class 日历对象 {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        Date d = new Date();
        cal.setTime(d);  //对日历进行赋值

        //获取某个内容
        int year = cal.get(Calendar.YEAR);
        int month = cal.get(Calendar.MONTH);
        int date = cal.get(Calendar.DAY_OF_MONTH);
        System.out.println(year+":"+(month+1)+":"+date);

        //进行修改
        cal.set(Calendar.MONTH, 3);
        year = cal.get(Calendar.YEAR);
        month = cal.get(Calendar.MONTH);
        date = cal.get(Calendar.DAY_OF_MONTH);
        System.out.println(year+":"+(month+1)+":"+date);

        cal.set(Calendar.MONTH, 13);
        year = cal.get(Calendar.YEAR);
        month = cal.get(Calendar.MONTH);
        date = cal.get(Calendar.DAY_OF_MONTH);
        System.out.println(year+":"+(month+1)+":"+date);

        //添加和减少

        cal.add(Calendar.MONTH, -1);
        year = cal.get(Calendar.YEAR);
        month = cal.get(Calendar.MONTH);
        date = cal.get(Calendar.DAY_OF_MONTH);
        System.out.println(year+":"+(month+1)+":"+date);
    }
    
}

```


## JDK八新增

### 8和7的区别

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162150575.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162150510.png)

方法不重要,不需要记,会查就好了,需要记得是这个静态和非静态方法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162224828.png)


```java
        //获取时区
        //Set<String> availableZoneIds = ZoneId.getAvailableZoneIds();
        //System.out.println(availableZoneIds);

        //获取系统时区
        ZoneId system = ZoneId.systemDefault();
        System.out.println(system);

        //获取指定的时区
        ZoneId queding = ZoneId.of("America/Grenada");
        System.out.println(queding);

        //获取当前时间戳
        Instant now = Instant.now();
        System.out.println(now);

        //获取当前instant对象
        Instant MillSecond = Instant.ofEpochMilli(0);
        System.out.println(MillSecond);

        Instant nm = Instant.ofEpochSecond(1, 1000000000);
        System.out.println(nm);

        Instant second = Instant.ofEpochSecond(0);
        System.out.println(second);

        //指定时区对象
        Instant ins = Instant.now();
        String string = "Asia/Kuching";
        ZonedDateTime zone1 = ins.atZone(ZoneId.of(string));
        System.out.println(zone1);
```

### instant

```java
        /*
            static Instant now() 获取当前时间的Instant对象(标准时间)
            static Instant ofXxxx(long epochMilli) 根据(秒/毫秒/纳秒)获取Instant对象
            ZonedDateTime atZone(ZoneIdzone) 指定时区
            boolean isxxx(Instant otherInstant) 判断系列的方法
            Instant minusXxx(long millisToSubtract) 减少时间系列的方法
            Instant plusXxx(long millisToSubtract) 增加时间系列的方法
        */
        //1.获取当前时间的Instant对象(标准时间)
        Instant now = Instant.now();//获取标准区域的时间
        System.out.println(now);

        //2.根据(秒/毫秒/纳秒)获取Instant对象
        Instant instant1 = Instant.ofEpochMilli(0L);
        System.out.println(instant1);//1970-01-01T00:00:00z

        Instant instant2 = Instant.ofEpochSecond(1L);
        System.out.println(instant2);//1970-01-01T00:00:01Z

        Instant instant3 = Instant.ofEpochSecond(1L, 1000000000L);
        System.out.println(instant3);//1970-01-01T00:00:027

        //3. 指定时区
        ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));
        System.out.println(time);


        //4.isXxx 判断
        Instant instant4=Instant.ofEpochMilli(0L);
        Instant instant5 =Instant.ofEpochMilli(1000L);

        //5.用于时间的判断
        //isBefore:判断调用者代表的时间是否在参数表示时间的前面
        boolean result1=instant4.isBefore(instant5);
        System.out.println(result1);//true

        //isAfter:判断调用者代表的时间是否在参数表示时间的后面
        boolean result2 = instant4.isAfter(instant5);
        System.out.println(result2);//false

        //6.Instant minusXxx(long millisToSubtract) 减少时间系列的方法
        Instant instant6 =Instant.ofEpochMilli(3000L);
        System.out.println(instant6);//1970-01-01T00:00:03Z

        Instant instant7 =instant6.minusSeconds(1);
        System.out.println(instant7);//1970-01-01T00:00:02Z
```

### zoneDatetime

```java
/*
            static ZonedDateTime now() 获取当前时间的ZonedDateTime对象
            static ZonedDateTime ofXxxx(。。。) 获取指定时间的ZonedDateTime对象
            ZonedDateTime withXxx(时间) 修改时间系列的方法
            ZonedDateTime minusXxx(时间) 减少时间系列的方法
            ZonedDateTime plusXxx(时间) 增加时间系列的方法
         */
//1.获取当前时间对象(带时区)
ZonedDateTime now = ZonedDateTime.now();
System.out.println(now);

//2.获取指定的时间对象(带时区)1/年月日时分秒纳秒方式指定
ZonedDateTime time1 = ZonedDateTime.of(2023, 10, 1,
                                       11, 12, 12, 0, ZoneId.of("Asia/Shanghai"));
System.out.println(time1);

//通过Instant + 时区的方式指定获取时间对象
Instant instant = Instant.ofEpochMilli(0L);
ZoneId zoneId = ZoneId.of("Asia/Shanghai");
ZonedDateTime time2 = ZonedDateTime.ofInstant(instant, zoneId);
System.out.println(time2);


//3.withXxx 修改时间系列的方法
ZonedDateTime time3 = time2.withYear(2000);
System.out.println(time3);

//4. 减少时间
ZonedDateTime time4 = time3.minusYears(1);
System.out.println(time4);

//5.增加时间
ZonedDateTime time5 = time4.plusYears(1);
System.out.println(time5);
```


### 4.4DateTimeFormatter   用于时间的格式化和解析

```java
/*
            static DateTimeFormatter ofPattern(格式) 获取格式对象
            String format(时间对象) 按照指定方式格式化
        */
//获取时间对象
ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));

// 解析/格式化器
DateTimeFormatter dtf1=DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm;ss EE a");
// 格式化
System.out.println(dtf1.format(time));
```

### localdate
```java
    LocalDate nowDate = LocalDate.now();
    System.out.println("今天的日期:" + nowDate);  //直接就是年月日
    //2.获取指定的时间的日历对象
    LocalDate ldDate = LocalDate.of(2023, 1, 1); //获取指定的年月日
    System.out.println("指定日期:" + ldDate);

    System.out.println("=============================");

    //3.get系列方法获取日历中的每一个属性值//获取年
    int year = ldDate.getYear();
    System.out.println("year: " + year);
    //获取月//方式一:
    Month m = ldDate.getMonth();
    System.out.println(m);
    System.out.println(m.getValue());

    //方式二:
    int month = ldDate.getMonthValue();
    System.out.println("month: " + month);


    //获取日
    int day = ldDate.getDayOfMonth();
    System.out.println("day:" + day);

    //获取一年的第几天
    int dayofYear = ldDate.getDayOfYear();
    System.out.println("dayOfYear:" + dayofYear);

    //获取星期
    java.time.DayOfWeek dayOfWeek = ldDate.getDayOfWeek();
    System.out.println(dayOfWeek);
    System.out.println(dayOfWeek.getValue());

    //is开头的方法表示判断
    System.out.println(ldDate.isBefore(ldDate));
    System.out.println(ldDate.isAfter(ldDate));

    //with开头的方法表示修改，只能修改年月日
    LocalDate withLocalDate = ldDate.withYear(2000);
    System.out.println(withLocalDate);

    //minus开头的方法表示减少，只能减少年月日
    LocalDate minusLocalDate = ldDate.minusYears(1);
    System.out.println(minusLocalDate);


    //plus开头的方法表示增加，只能增加年月日
    LocalDate plusLocalDate = ldDate.plusDays(1);
    System.out.println(plusLocalDate);

    //-------------
    // 判断今天是否是你的生日
    LocalDate birDate = LocalDate.of(2000, 1, 1);
    LocalDate nowDate1 = LocalDate.now();

    MonthDay birMd = MonthDay.of(birDate.getMonthValue(), birDate.getDayOfMonth());
    MonthDay nowMd = MonthDay.from(nowDate1);

    System.out.println("今天是你的生日吗? " + birMd.equals(nowMd));//今天是你的生日吗?
```

### localDateTime

```java
## 4.6 LocalTime  时、分、秒

```java
// 获取本地时间的日历对象。(包含 时分秒)
LocalTime nowTime = LocalTime.now();
System.out.println("今天的时间:" + nowTime);

int hour = nowTime.getHour();//时
System.out.println("hour: " + hour);

int minute = nowTime.getMinute();//分
System.out.println("minute: " + minute);

int second = nowTime.getSecond();//秒
System.out.println("second:" + second);

int nano = nowTime.getNano();//纳秒
System.out.println("nano:" + nano);
System.out.println("------------------------------------");
System.out.println(LocalTime.of(8, 20));//时分
System.out.println(LocalTime.of(8, 20, 30));//时分秒
System.out.println(LocalTime.of(8, 20, 30, 150));//时分秒纳秒
LocalTime mTime = LocalTime.of(8, 20, 30, 150);

//is系列的方法
System.out.println(nowTime.isBefore(mTime));
System.out.println(nowTime.isAfter(mTime));

//with系列的方法，只能修改时、分、秒
System.out.println(nowTime.withHour(10));

//plus系列的方法，只能修改时、分、秒
System.out.println(nowTime.plusHours(10));
```



### 4.7 LocalDateTime  年、月、日、时、分、秒

```java
// 当前时间的的日历对象(包含年月日时分秒)
LocalDateTime nowDateTime = LocalDateTime.now();

System.out.println("今天是:" + nowDateTime);//今天是：
System.out.println(nowDateTime.getYear());//年
System.out.println(nowDateTime.getMonthValue());//月
System.out.println(nowDateTime.getDayOfMonth());//日
System.out.println(nowDateTime.getHour());//时
System.out.println(nowDateTime.getMinute());//分
System.out.println(nowDateTime.getSecond());//秒
System.out.println(nowDateTime.getNano());//纳秒
// 日:当年的第几天
System.out.println("dayofYear:" + nowDateTime.getDayOfYear());
//星期
System.out.println(nowDateTime.getDayOfWeek());
System.out.println(nowDateTime.getDayOfWeek().getValue());
//月份
System.out.println(nowDateTime.getMonth());
System.out.println(nowDateTime.getMonth().getValue());

LocalDate ld = nowDateTime.toLocalDate();
System.out.println(ld);

LocalTime lt = nowDateTime.toLocalTime();
System.out.println(lt.getHour());
System.out.println(lt.getMinute());
System.out.println(lt.getSecond());
```




在Java中，ZoneID、Instant、ZonedDateTime和DateTimeFormatter这些类和接口用于处理日期、时间和时区相关的操作。下面是它们各自的功能说明：

1. ZoneID：ZoneID类表示一个特定的时区。它提供了访问和操作时区的方法，比如获取可用的时区列表、根据时区ID获取时区对象等。

2. Instant：Instant类代表从1970年1月1日00:00:00（格林威治时间）开始经过的时间（以秒为单位）。它用于处理瞬时时间点，可以用来进行时间戳的转换、计算时间间隔等。

3. ZonedDateTime：ZonedDateTime类是在Instant的基础上加入了时区信息的日期时间表示。它包含了日期、时间和时区，并支持对日期时间的各种操作，比如获取年、月、日、时、分、秒等，以及转换时区、计算时间差等。

4. DateTimeFormatter：DateTimeFormatter类可以用来格式化和解析日期时间字符串。它提供了一系列预定义的格式模式，也支持自定义格式。可以使用DateTimeFormatter将日期时间对象格式化为字符串，或者将字符串解析为日期时间对象。

综合来说，ZoneID用于管理时区，Instant用于处理瞬时时间点，ZonedDateTime用于处理具有时区信息的日期时间，而DateTimeFormatter用于格式化和解析日期时间字符串。

Date获取只能获取年月日,TIme只能获取时分秒

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162234048.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162235095.png)



### duration（秒，纳，秒）

```java
        LocalDateTime today = LocalDateTime.now();
        System.out.println(today);

        // 出生的日期时间对象
        LocalDateTime birthDate = LocalDateTime.of(2000, 1, 1, 0, 0, 0);
        System.out.println(birthDate);

        Duration duration = Duration.between(birthDate, today);//第二个参数减第一个参数
        System.out.println("相差的时间间隔对象:" + duration);

        System.out.println("============================================");
        System.out.println(duration.toDays());//两个时间差的天数
        System.out.println(duration.toHours());//两个时间差的小时数
        System.out.println(duration.toMinutes());//两个时间差的分钟数
        System.out.println(duration.toMillis());//两个时间差的毫秒数
        System.out.println(duration.toNanos());//两个时间差的纳秒数
```

### period 年月日

```java
package demo.day2;

import java.time.LocalDate;
import java.time.Period;

public class period {
    public static void main(String[] args) {
        // 当前本地 年月日
        LocalDate today = LocalDate.now();
        System.out.println(today);

        // 生日的 年月日
        LocalDate birthDate = LocalDate.of(2000, 1, 1);
        System.out.println(birthDate);

        Period period = Period.between(birthDate, today);//第二个参数减第一个参数

        System.out.println("相差的时间间隔对象:" + period);
        System.out.println(period.getYears());
        System.out.println(period.getMonths());
        System.out.println(period.getDays());

        System.out.println(period.toTotalMonths());
    }
    
}

```


### ChronoUnit 时间间隔（所有单位）

```java
// 当前时间
LocalDateTime today = LocalDateTime.now();
System.out.println(today);
// 生日时间
LocalDateTime birthDate = LocalDateTime.of(2000, 1, 1,0, 0, 0);
System.out.println(birthDate);

System.out.println("相差的年数:" + ChronoUnit.YEARS.between(birthDate, today));
System.out.println("相差的月数:" + ChronoUnit.MONTHS.between(birthDate, today));
System.out.println("相差的周数:" + ChronoUnit.WEEKS.between(birthDate, today));
System.out.println("相差的天数:" + ChronoUnit.DAYS.between(birthDate, today));
System.out.println("相差的时数:" + ChronoUnit.HOURS.between(birthDate, today));
System.out.println("相差的分数:" + ChronoUnit.MINUTES.between(birthDate, today));
System.out.println("相差的秒数:" + ChronoUnit.SECONDS.between(birthDate, today));
System.out.println("相差的毫秒数:" + ChronoUnit.MILLIS.between(birthDate, today));
System.out.println("相差的微秒数:" + ChronoUnit.MICROS.between(birthDate, today));
System.out.println("相差的纳秒数:" + ChronoUnit.NANOS.between(birthDate, today));
System.out.println("相差的半天数:" + ChronoUnit.HALF_DAYS.between(birthDate, today));
System.out.println("相差的十年数:" + ChronoUnit.DECADES.between(birthDate, today));
System.out.println("相差的世纪(百年)数:" + ChronoUnit.CENTURIES.between(birthDate, today));
System.out.println("相差的千年数:" + ChronoUnit.MILLENNIA.between(birthDate, today));
System.out.println("相差的纪元数:" + ChronoUnit.ERAS.between(birthDate, today));
```

# 包装类

## 5.1 概述

Java提供了两个类型系统，基本类型与引用类型，使用基本类型在于效率，然而很多情况，会创建对象使用，因为对象可以做更多的功能，如果想要我们的基本类型像对象一样操作，就可以使用基本类型对应的包装类，如下：

|基本类型|对应的包装类（位于java.lang包中）|
|---|---|
|byte|Byte|
|short|Short|
|int|**Integer**|
|long|Long|
|float|Float|
|double|Double|
|char|**Character**|
|boolean|Boolean|

## 5.2 Integer类

- Integer类概述
    
    包装一个对象中的原始类型 int 的值
    
- Integer类构造方法及静态方法
    

|方法名|说明|
|---|---|
|public Integer(int value)|根据 int 值创建 Integer 对象(过时)|
|public Integer(String s)|根据 String 值创建 Integer 对象(过时)|
|public static Integer valueOf(int i)|返回表示指定的 int 值的 Integer 实例|
|public static Integer valueOf(String s)|返回保存指定String值的 Integer 对象|
|static string tobinarystring(int i)|得到二进制|
|static string tooctalstring(int i)|得到八进制|
|static string toHexstring(int i)|得到十六进制|
|static int parseInt(string s)|将字符串类型的整数转成int类型的整数|

### 定义
**过时**
public Integer(int value)：根据 int 值创建 Integer 对象(过时)

```java
//public Integer(int value)：根据 int 值创建 Integer 对象(过时)
Integer i1 = new Integer(100);
System.out.println(i1);

//public Integer(String s)：根据 String 值创建 Integer 对象(过时)
Integer i2 = new Integer("100");
//Integer i2 = new Integer("abc"); //NumberFormatException
System.out.println(i2);
System.out.println("--------");

//public static Integer valueOf(int i)：返回表示指定的 int 值的 Integer 实例
Integer i3 = Integer.valueOf(100);
System.out.println(i3);

//public static Integer valueOf(String s)：返回保存指定String值的Integer对象 
Integer i4 = Integer.valueOf("100");
System.out.println(i4);
```

### 转换二进制

```java
        /*
            public static string tobinarystring(int i) 得到二进制
            public static string tooctalstring(int i) 得到八进制
            public static string toHexstring(int i) 得到十六进制
            public static int parseInt(string s) 将字符串类型的整数转成int类型的整数
        */

        //1.把整数转成二进制，十六进制
        String str1 = Integer.toBinaryString(100);
        System.out.println(str1);//1100100

        //2.把整数转成八进制
        String str2 = Integer.toOctalString(100);
        System.out.println(str2);//144

        //3.把整数转成十六进制
        String str3 = Integer.toHexString(100);
        System.out.println(str3);//64

        //4.将字符串类型的整数转成int类型的整数
        //强类型语言:每种数据在java中都有各自的数据类型
        //在计算的时候，如果不是同一种数据类型，是无法直接计算的。
        int i = Integer.parseInt("123");
        System.out.println(i);
        System.out.println(i + 1);//124
        //细节1:
        //在类型转换的时候，括号中的参数只能是数字不能是其他，否则代码会报错
        //细节2:
        //8种包装类当中，除了Character都有对应的parseXxx的方法，进行类型转换
        String str = "true";
        boolean b = Boolean.parseBoolean(str);
        System.out.println(b);
```


## 5.3 装箱与拆箱

基本类型与对应的包装类对象之间，来回转换的过程称为”装箱“与”拆箱“：

- **装箱**：从基本类型转换为对应的包装类对象。
    
- **拆箱**：从包装类对象转换为对应的基本类型。
    

用Integer与 int为例：（看懂代码即可）

基本数值---->包装对象

> nteger i = new Integer(4);//使用构造函数函数  
    Integer iii = Integer.valueOf(4);//使用包装类中的valueOf方法

包装对象---->基本数值

> int num = i.intValue();

## 5.4 自动装箱与自动拆箱

由于我们经常要做基本类型与包装类之间的转换，从Java 5（JDK 1.5）开始，基本类型与包装类的装箱、拆箱动作可以自动完成。例如：

Integer i = 4;//自动装箱。相当于Integer i = Integer.valueOf(4);  
i = i + 5;//等号右边：将i对象转成基本数值(自动拆箱) i.intValue() + 5;  
//加法运算完成后，再次装箱，把基本数值转成对象。

## 5.5 基本类型与字符串之间的转换

### 基本类型转换为String

- 转换方式
- 方式一：直接在数字后加一个空字符串
- 方式二：通过String类静态方法valueOf()
- 示例代码

```java
public class IntegerDemo {
    public static void main(String[] args) {
        //int --- String
        int number = 100;
        //方式1
        String s1 = number + "";
        System.out.println(s1);
        //方式2
        //public static String valueOf(int i)
        String s2 = String.valueOf(number);
        System.out.println(s2);
        System.out.println("--------");
    }
}
```

### String转换成基本类型 

除了Character类之外，其他所有包装类都具有parseXxx静态方法可以将字符串参数转换为*对应的基本类型*：

- `public static byte parseByte(String s)`：将字符串参数转换为对应的byte基本类型。
- `public static short parseShort(String s)`：将字符串参数转换为对应的short基本类型。
- **`public static int parseInt(String s)`：将字符串参数转换为对应的int基本类型。**
- **`public static long parseLong(String s)`：将字符串参数转换为对应的long基本类型。**
- `public static float parseFloat(String s)`：将字符串参数转换为对应的float基本类型。
- `public static double parseDouble(String s)`：将字符串参数转换为对应的double基本类型。
- `public static boolean parseBoolean(String s)`：将字符串参数转换为对应的boolean基本类型。

代码使用（仅以Integer类的静态方法parseXxx为例）如：

- 转换方式
  - 方式一：先将字符串数字转成Integer，再调用valueOf()方法
  - 方式二：通过Integer静态方法parseInt()进行转换
- 示例代码

```java
public class IntegerDemo {
    public static void main(String[] args) {
        //String --- int
        String s = "100";
        //方式1：String --- Integer --- int
        Integer i = Integer.valueOf(s);
        //public int intValue()
        int x = i.intValue();
        System.out.println(x);
        //方式2
        //public static int parseInt(String s)
        int y = Integer.parseInt(s);
        System.out.println(y);
    }
}
```

> 注意:如果字符串参数的内容无法正确转换为对应的基本类型，则会抛出`java.lang.NumberFormatException`异常。


# 算法

## 查找算法

> 顺序查找


> 二分查找


> 插值查找

二分算法的优化,通过逼近来实现这个查找
关键代码是
`int mid = left + (target - a[left]) / (a[right] - a[left]) * (right - left);`

> 斐波那契查找

利用0.618的分割比进行查找这个数字
关键代码是
`int mid =(int)((right - left) * (1.0 / 1.618) + left) ;`

> 分块查找

就是将数组中的数据划分为几个块,前一个块的所有数据小于后一个块的所有数据,我们以每一个块的最大值来进行分割
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307181034249.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307181044450.png)



# 集合

## day3

### 182集

Array是一个类,里面封装的一般是静态方法,使用的时候我们通过类名的方式来进行使用

常见的一些方法


1. toString将数组转化为字符串,可以让我们遍历数组的时候更加方便,不用在写循环进行便利了
    
2. binarySearch进行二分搜索,如果找到我们返回下标,如果找不到,我们返回负的插入点-1,,为什么减1是因为可能有插入点为0 的情况
    
3. 拷贝数组,数组的长度,和新数组的长度,这个有两个参数copyOf,copyOfRange,包头不包尾,包左不包右,
    
4. fill将数组填充同一个数字
    
5. sort方法,进行快速排序,匿名内部类在看一下![image-20230718175837358](file://D:\code\%E8%B4%B4%E5%9B%BE\image-20230718175837358.png?lastModify=1690768783)
    

-![image-20230718180610054](file://D:\code\%E8%B4%B4%E5%9B%BE\image-20230718180610054.png?lastModify=1690768783)

### Lambda表达式

简化书写匿名内部类

![image-20230718180905445](file://D:\code\%E8%B4%B4%E5%9B%BE\image-20230718180905445.png?lastModify=1690768783)

()里面是形参->没有意义,设为La mbda的固定格式

注意点

![image-20230718183557484](file://D:\code\%E8%B4%B4%E5%9B%BE\image-20230718183557484.png?lastModify=1690768783)
## 泛型

```java
package heima_study.day5集合进阶;

import java.util.ArrayList;

public class 泛型的通配符 {
    public static void main(String[] args) {
        /*
         * 泛型不具备继承性,但是数据具有继承性
         */
        ArrayList<FU> list = new ArrayList<>();
        ArrayList<ZI> list2 = new ArrayList<>();
        ArrayList<YE> list3 = new ArrayList<>();
        method(list);
        // method(list2); //此时这个代码就是错误的,因为这个list2时类型ZI无有法传递

        // 当定义一个泛型的时候,所有的数据都能传递
        method1(list2);
        method1(list3);

        // 当时一个? extends E的时候,所有继承E的都能使用
        method3(list);
        method3(list3);
        method3(list2);

        // 当定义一个? super E的时候,所有E的父类都能使用

        // method4(list2); // 子无法继承
        method4(list); // 本身
        method4(list3); // 父类

    }

    public static void method(ArrayList<FU> list) {

    }

    public static <E> void method1(ArrayList<E> list) {

    }

    public static void method3(ArrayList<? extends YE> list) {

    }

    public static void method4(ArrayList<? super FU> list) {

    }
}

class YE {

}

class FU extends YE {

}

class ZI extends FU {

}

```



## 数据结构

