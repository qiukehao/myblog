---
{"dg-publish":true,"permalink":"/02java//01java-se/15-api/","dgPassFrontmatter":true}
---

# 常见的 API
## Math
从 JDK 版本 1 开始的, 用来计算的一些方法
这里面定义了两个常量的 PI 和 E 这两个是最接近 pi 的值和最接近对数的值

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181026116.png)
1. Abs (int a ) 取绝对值
2. Ceil (double a)向上取整
3. Floor (double a )向下取整
4. Round (float a)四舍五入
5. Max (int a, int b) 取最大值
6. Pow (double a, double b) a 的 b 次幂
7. Random () 返回值为 double 的随机数, 范围是[ 0.0 , 1.0 );  ]
举例
```java

    public static void main(String[] args) {
        System.out.println(Math.max(1, 2));// 返回两个数中较大的数
        System.out.println(Math.min(1, 2));// 返回两个数之间较小的数
        System.out.println(Math.abs(-1)); // 返回一个数的绝对值
        System.out.println(Math.ceil(1.5));// 向上取整,ceil天花板的意思
        System.out.println(Math.floor(1.5));// 向下取整,floor地板的意思,正好对应着向上取整和向下取整
        System.out.println(Math.round(1.5));// round四舍五入
        System.out.println(Math.round(1.4));// round四舍五入
        System.out.println(Math.pow(10, 2)); // 对一个数进行平方,a的b次方
        System.out.println(Math.sqrt(100)); // 对一个数进行开方
        System.out.println(Math.random()); // 返回0-1的整数
    }
```
其中有一个点需要注意
**Abs**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181028086.png)
这属于一个小 bug
当我们的数据比较大的时候, 我们可以用 Math, absExact 来进行使用, 这个并不能纠错, 但是可以提示我们错误, 原来的是不提示错误直接输出了.
### 开平方 sqrt, 开立方根 cbrt
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181034531.png)

## System
我们通过这个 System 名直接调用
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309171522309.png)
我们查看这个 java 的参考文档，发现这个 System 属于这个 java.long 包下, 所以不需要我们额外的进行导包, 我们可以直接进行调用.
> [!info]
> 下面我们对其几个常用的方法进行研究
### Exit
0, 表示当前虚拟机是正常停止
非 0, 表示当前虚拟机是非正常停止
```java
常见的用法
System.exit(0);
System.exit(1);
```
### CurrentTimeMills
参考文档中给出的解释是
```
public static long currentTimeMillis()
以毫秒为单位返回当前时间。 请注意，虽然返回值的时间单位是毫秒，但值的粒度取决于底层操作系统，并且可能更大。 例如，许多操作系统以几十毫秒为单位测量时间。 
有关“计算机时间”和协调世界时（UTC）之间可能出现的轻微差异的讨论，请参阅类Date的说明。 
结果 
当前时间与UTC时间1970年1月1日午夜之间的差异，以毫秒为单位。 
```
计算机的时间原点
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305181057088.png)

由于时区的影响, 我们获取的时间原点是
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/20230518105749.png)
1 s=1000 ms
1 ms=1000 us
1 us=1000 ns

```java
        System.out.println("current time ");
        System.out.println(System.currentTimeMillis());
```

我们通过这个代码可以获得这个程序执行所需的总时间, 之后我们可以参考这个 Date 类中的时间转化, 将这个时间戳转化为具体的时间值
附上这个时间戳转化的网站
[时间戳转化](https://tool.lu/timestamp/)
>[! warning]  
>值得注意的是这个 currentTimeMillis 获得的是这个毫秒的时间, 我们在转化的时候要注意
### Arraycopy

```java
int [] arr1 = {1,2,3,4,5,6};
int [] arr2 = new int[6];
System.arraycopy(arr1,0,arr2,0,6);
```

把 arr 1 数组中的数据拷贝到 arr2中
1. 参数一: 数据源，要拷贝的数据从哪个数组而来
2. 参数二: 从数据源数组中的第几个索引开始拷贝
3. 参数三: 目的地，我要把数据拷贝到哪个数组中
4. 参数四: 目的地数组的索引。
5. 参数五: 拷贝的个数

```java
int [] arr1 = {1,2,3,4,5,6,7,8,9,10};
int [] arr2 = new int[10];
System.arraycopy(arr1,0,arr2,4,3);
//0 0 0 0 1 2 3 0 0 0
```

#### 注意点
1. 拷贝的对象可以是基本数据类型, 也可以是引用数据类型
2. 如果这个拷贝的数组都是基本数据类型, 那么两者的数据类型必须一模一样, 否则就会报错
3. 在拷贝的时候数组不能越界
4. 如果数据源数组和目的地数组都是引用数据类型，那么子类类型可以赋值给父类类型, 比如说 Student 类型可以赋值给 Person 类型
## Runtime
Runtime 也是属于 java.long 包下的, 所以我们并不需要对其进行单独的导包
- 每个 Java 应用程序都有一个类 `Runtime` 实例，它允许应用程序与运行应用程序的环境进行交互。可以从 `getRuntime` 方法获得当前运行时。
Runtime 和后面的多线程是有联系的, 在那一章节里我在详细的对它进行解释
[[02java/笔记/01javaSE基础笔记/25-多线程\|02java/笔记/01javaSE基础笔记/25-多线程]]
### GetRuntime ()
返回当前应用程序所关联的的系统进程
```java
public static Runtime getRuntime()//这是一个静态函数
```
Runtime 类的构造方法是私有的（private），这意味着无法通过使用 new 关键字来实例化（构建）Runtime 类的对象
Runtime类提供了一个静态方法GetRuntime()，该方法返回Runtime类的唯一实例。通过调用GetRuntime()方法，您可以获取对该实例的引用
> [!note] 
> 常用方法举例

```java
    public static void main(String[] args) throws IOException {
	System.out.println(Runtime.getRuntime().availableProcessors());// 获取cpu的线程数
        System.out.println(Runtime.getRuntime().freeMemory());// 获取空闲内存
        System.out.println(Runtime.getRuntime().totalMemory());// 获取总内存
        System.out.println(Runtime.getRuntime().maxMemory());// 获取最大内存
=
        Runtime.getRuntime().exec("shutdowm -s -t 时间");//关机按钮
        Runtime.getRuntime().exec("shutdowm -a");//停止关机

    }
```
其中对于这个 execAPI 文档里面是这样解释的
```
public Process exec​(String command) throws IOException
在单独的进程中执行指定的字符串命令。 
这是一种方便的方法。 调用窗体exec(command)行为与调用exec (command, null, null) 。 

参数 
command - 指定的系统命令。 
结果 
用于管理子进程的新Process对象 
```

执行该方法, 系统会爆出异常, 因此需要我们主动的去抛出异常, 或者需要我们进行这个 try catch 捕获异常
[[02java/笔记/01javaSE基础笔记/19-异常的学习笔记\|02java/笔记/01javaSE基础笔记/19-异常的学习笔记]]
## Object
Object 是 java 中的顶级父类，所有的类都直接或间接的继承于 Object 类
Object 只有一个空参构造，我们通过空参构造进行创建对象
我们自己新建一个类，它默认继承这个 object 类的

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191502132.png)
### ToString
Object.ToString () 返回的是一个字符串---包名加类名, 加地址值
当我们打印一个对象的时候, 底层会调用, 对象的 toString 方法, 把对象变成字符串.
java 是一个面向对象语言, 而所有的对象都继承于这个 object 类, 所以所有的对象都具有这个 toString 方法, 我们在使用这个 System.out.println 方法的时候就是默认打印这个对象的 toString 方法
### Equals
我们查看这个方法的源代码发现这个是通过 this== object 来进行比较的, 这种比较是比较的两个对象的地址, 但是大多数情况下我们是比较的对象里面的内容, 因此我们在这种情况下我们一般选择进行重写
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191454724.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191501801.png)
### Clone
#### 浅克隆
浅克隆是将 A 对象的属性值, 拷贝给 B 对象, 也叫对象拷贝, 对象复制, 对象的变量属性地址是相同的
#### 深克隆
深克隆对于基本数据类型也是拷贝地址, 但是对于引用数据类型, 就是新建一个空间, 然后进行存放数据的, 两者之间的地址内容是不相同的
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191513598.png)

父类的 clone 是默认浅克隆, 如果我们想实现这个深克隆, 我们要自己进行重写.

由于对象的数据类型不是确定的, 一维数组有一维数组的写法, 二维数组有二维数组的写法, 为了方便我们进行编程, 我们通过第三方的工具可以实现这个重写功能;
## Objects
在 java 中我们不能用字符 null 来调用方法否则这个系统会报错
Objects 类所在包是在 java. Util 包下，因此在使用的时候需要进行导包。并且 Objects 类是被 final 修饰的，因此该类不能被继承。
暂时先不了解，等用到自己在查阅参考文档

## BigInteger 类
常考博文-我写的

### 引入
Java 整数中只有四种类型, byte, short, int, long
其中分别是 1,2,4,8 个字节数
平时在存储整数的时候，Java 中默认是 int 类型，int 类型有取值范围：-2147483648 ~ 2147483647。如果数字过大，我们可以使用 long 类型，但是如果 long 类型也表示不下怎么办呢？ 
就需要用到 BigInteger，可以理解为：大的整数。
有多大呢？理论上最大到 42 亿的 21 亿次方基本上在内存撑爆之前，都无法达到这个上限。
### 概述
BigInteger 所在包是在 java. Math 包下，因此在使用的时候就需要进行导包。我们可以使用 BigInteger 类进行大整数的计算
对象一旦创建, 内部的对象值是不能修改的
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

这种构造方法构造的不是一个确定的整数, 而是一个随即数

```java
BigInteger test1 = new BigInteger("99999999999999999999999");
```

这种构造方法可以构造指定大小的数字, 引号必须是整数,

```java
BigInteger test3 = new BigInteger("100",2);
```

可以构建指定进制的数字, 引号里面的数字必须符合进制

```java
BigInteger test4 = BigInteger.valueOf(9999999999999999999999999);
```

创建静态对象, 但是这个静态对象的范围比较小, 我们一般不用


### 常见成员方法
虽然说这个对象简称大数, 但是实际上它并不是一个数, 而是一个对象, 因为 java 不允许对象使用操作符, 因此操作大数的时候必须使用方法调用, 折叶就是为什么要使用这个 add,substract 的原因
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

BigInterget 对象的值是不能进行修改的, 而是我们产生了一个新的 BigInterger 对象的值

```java
//5.对象一旦创建内部的数据不能发生改变
BigInteger bd9 =BigInteger.valueOf(1);
BigInteger bd10 =BigInteger.valueOf(2);
//此时，不会修改参与计算的BigInteger对象中的借，而是产生了一个新的BigInteger对象记录
BigInteger result=bd9.add(bd10);
System.out.println(result);//3
```


## BigDecimal 类

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

**这样的结果其实就是一个丢失精度的结果**
如何解决呢, 我们可以使用这个 BigDecimal 来进行计算
BigDecimal 类能计算出准确结果。
调用 BigDecimal. Valueof (n， e)返回 BigDecimal 示例，其值为**nx 10 e 次方**
**利用这个大数进行浮点数的减法运算**
当我们进行浮点数的减法运算的时候可能会丢失精度, 比如 2.0-1.1=0.8999999999999
但是如果我们用这个 BigDecimal. Substract 的话就不会丢失结果
BigDecimal. ValueOf (2, 0 ). Substract (BigDecimal. ValueOf (11,
运算的结果精确为**0.9**。
### 常见的构造方法
![1576134383441.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202305191719099.png)
