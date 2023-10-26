---
{"dg-publish":true,"permalink":"/02java//01java-se/18-date/","dgPassFrontmatter":true}
---


Date 的定义,
在开始研究这个之前我们首先要能够明白一点，这个 Date 其实本质上是一个对象，我们通过这个对象可以去构建变量，知道这个之后就可以开展后续的研究了
# JDK 通用
## Date 类的构造方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309201901030.png)

**测试**
获取当前的时间
```java
        // 构造这个日期对象Date ,直接用这个new方法来构建是自动获取这个当前的时间.
        Date date = new Date();
        System.out.println(date);
        //输出了当前的时间2023/9/20
```
获取指定的时间
```java
        // 如果我想指定一个时间呢?
        Date date2 = new Date(2023, 2, 2);
        System.out.println(date2);
        //输出时间是Fri Mar 02 00:00:00 CST 3923
```
此时你就会发现输出的时间和你指定的时间不一样,我们查询这个 API 文档可以知道
这个指定日期的构建方法其中的年是 1970+? 月是 0-11
解释一下就是你如果年份是 1, 那么输出的就是 1971, 如果是 200 输出的就是 2170,
月份是从 0-11, 你输入 0 表示一月, 输入 2 表示 3 月
## Date 的常用内部方法
Date 的大多数方法都已经过时了, 已经出现了比其更加高效, 方便的方法, 为数不多中还在使用的方法有下面两个, 获取当前时间, 和设置当前时间
Date 的 gettime 方法
Date 的 settime 方法
注意使用 date 的时候导包一定要导入 utils 包下面的, 否则就会无法正确识别了
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

## SimpleDateFormat 类
顾名思义, 简单日期格式. 就是将上面比较不太令人懂的时间戳`1695208554901`换成我们熟悉的简单格式, 比如说字符串
作用是:格式化 
有下面两种用法
- 将时间变成我们喜欢的格式
```java
        SimpleDateFormat sdf2 = new SimpleDateFormat("yyyy - MM - dd, HH - mm - ss");
        String format = sdf2.format(date2);
        System.out.println(format);
```
- 将字符串表示的对象转换为 Date 格式
```java
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 第DD天第ww周 一个月的第WW周 E HH时mm分ss秒");
        String s = "2023年07月16日 第197天第29周 一个月的第04周 周日 20时35分55秒";
        Date date = sdf.parse(s);
        System.out.println(date);
```

> [!warning] 
> 值得注意的时这个 sdf.parse 是由两个参数的, 但是第二个参数我们可以先不用了解, 先传递一个字符串就好了, 此时系统会报错, 我们可以通过抛出异常, 或者 try catch 来进行解决

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162002972.png)
## Calendar

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162109972.png)


![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162114235.png)

calendar 是一个抽象的类, 不能够直接的创建对象, calendar 因此提供了一个类方法 getInstance 可以用来获取此类型的通用对象
```java
Calendar cal = Calendar.getInstance();
```
除此之外我们还要注意这个外国的日期和周几和中国的不太一样, 不太符合我们的观感, 对于他们来说 1 代表周日, 2 才代表周一, 这一点需要我们注意.
### calendar 的测试
#### get测试
```java
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        Date date = new Date();
        cal.setTime(date);
        int year = cal.get(Calendar.YEAR);
        int month = cal.get(Calendar.MONTH);
        int day = cal.get(Calendar.DAY_OF_MONTH); // 这一个月的第几天
        int day2 = cal.get(Calendar.DAY_OF_WEEK);// 这一周的第几天
        System.out.println("今天星期" + (day2 - 1));
        System.out.println(year + ":" + (month + 1) + ":" + day);

    }
```
#### set 测试
```java
package demo.day2;

import java.util.Calendar;
import java.util.Date;

public class 日历对象 {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        Date d = new Date();
        cal.setTime(d);  //对日历进行赋值
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

    }
    
}

```
#### 修改测试
```java
        //添加和减少

        cal.add(Calendar.MONTH, -1);
        year = cal.get(Calendar.YEAR);
        month = cal.get(Calendar.MONTH);
        date = cal.get(Calendar.DAY_OF_MONTH);
        System.out.println(year+":"+(month+1)+":"+date);
```

# JDK 八新增

## 8 和 7 的区别

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162150575.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162150510.png)
这个 Date 这一章节, 出了名的方法多, 而且很容易记混, 因为大多数都差不多, 对于此, 我们的解决办法时, 不需要特意的去记这些方法, 我们只需要会查就可以了

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

## Instant
instant 的意思时顺势点的意思, 其表示这个时间线上的瞬时点。 
该类在时间线上模拟单个瞬时点。可以用来在应用程序中记录事件时间戳。 
### 获取当前时间对象
```java
        Instant ins = Instant.now();
        System.out.println(ins);
```
我们首先通过这个 Instant. Now ()来获取这个 Instant 对象.输出之后发现其输出的并不是我们当前的系统时间, 别着急, 并不是它错了, 且往下继续看

### Static Instant ofXxxx (long epochMilli) 根据 (秒/毫秒/纳秒)获取 Instant 对象
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202002829.png)

```java
        //2.根据(秒/毫秒/纳秒)获取Instant对象
        Instant instant1 = Instant.ofEpochMilli(0L);
        System.out.println(instant1);//1970-01-01T00:00:00z 毫秒

        Instant instant2 = Instant.ofEpochSecond(1L);
        System.out.println(instant2);//1970-01-01T00:00:01Z  秒增加了一位

        Instant instant3 = Instant.ofEpochSecond(1L, 1000000000L);
        System.out.println(instant3);//1970-01-01T00:00:02z  //在一秒的标准上在加1000000000ns,刚好时两秒
```

### 指定时区
[[02java/笔记/01javaSE基础笔记/18-Date类#ZoneDatetime\|#ZoneDatetime]]
这个时区后面的 ZoneDatetime 会讲解, 此处放在这里是为了说明这个 Instant 的作用.
```java
        //3. 指定时区
        ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));
        System.out.println(time);
```
### 判断系列的方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202007335.png)

```java
        //4.isXxx 判断 总共时
        Instant instant4=Instant.ofEpochMilli(0L);
        Instant instant5 =Instant.ofEpochMilli(1000L);
       //isBefore:判断调用者代表的时间是否在参数表示时间的前面
        boolean result1=instant4.isBefore(instant5);
        System.out.println(result1);//true

        //isAfter:判断调用者代表的时间是否在参数表示时间的后面
        boolean result2 = instant4.isAfter(instant5);
        System.out.println(result2);//false
```
### 增加和减少的方法

```java
        //6.Instant minusXxx(long millisToSubtract) 减少时间系列的方法
        Instant instant6 =Instant.ofEpochMilli(3000L);
        System.out.println(instant6);//1970-01-01T00:00:03Z

        Instant instant7 =instant6.minusSeconds(1); //minus是减的意思,3-1=2
        System.out.println(instant7);//1970-01-01T00:00:02Z
```

## ZoneDatetime
- `ZonedDateTime` 是具有时区的日期时间的不可变表示。此类存储所有日期和时间字段，精度为纳秒和时区，区域偏移用于处理模糊的本地日期时间。例如，值“2007 年 10 月 2 日 13：45.30.123456789 + 02：00 在欧洲/巴黎时区”可以存储在 `ZonedDateTime` 。
- `ZonedDateTime`保持相当于三个单独对象的`LocalDateTime` ， `ZoneId`和已解决的`ZoneOffset` 。 偏移和本地日期时间用于在必要时定义瞬间。 区域ID用于获取偏移量变化的方式和时间的规则。 无法自由设置偏移，因为区域控制哪些偏移有效。
### 获取当前时间的 ZonedDateTime 对象
```java
//1.获取当前时间对象(带时区)
ZonedDateTime now = ZonedDateTime.now();
System.out.println(now);
//2023-09-20T20:15:44.395502500+08:00[Asia/Shanghai]
```
比如说我当前所处的时区就是 Asia/Shanghai
### 获取指定时间的 ZonedDateTime 对象
第一种方式, 直接指定这个时间对象和时区
```java
//2.获取指定的时间对象(带时区)1/年月日时分秒纳秒方式指定
ZonedDateTime time1 = ZonedDateTime.of(2023, 10, 1,
                                       11, 12, 12, 0, ZoneId.of("Asia/Shanghai"));
System.out.println(time1);
```
第二种方式,先获得这个时间, 在指定这个时区,
```java
//通过Instant + 时区的方式指定获取时间对象
Instant instant = Instant.ofEpochMilli(0L);  //获得时间
ZoneId zoneId = ZoneId.of("Asia/Shanghai");  //获得时区
ZonedDateTime time2 = ZonedDateTime.ofInstant(instant, zoneId); //指定时间,指定时区
System.out.println(time2);
```
### 修改时间的方法
```java
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
## DateTimeFormatter   用于时间的格式化和解析
其中这个 format 函数中传递的参数是 TemporalAccessor 类型的, 这个是一个接口, 实现这个接口的类在下面图片里面,Date 类不属于实现类, 因此不能进行使用.
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202034489.png)

- 用于打印和解析日期时间对象的格式化程序。
    此类提供打印和解析的主要应用程序入口点，并提供`DateTimeFormatter`常见实现：
    - 使用预定义常量，例如`ISO_LOCAL_DATE`
    - 使用模式字母，例如`uuuu-MMM-dd`
    - 使用本地化样式，例如`long`或`medium`
    更复杂的格式化器由`DateTimeFormatterBuilder`提供。
```java
		/*
            static DateTimeFormatter ofPattern(格式) 获取格式对象
            String format(时间对象) 按照指定方式格式化
        */
//获取时间对象
ZonedDateTime time = Instant.now().atZone(ZoneId.of("Asia/Shanghai"));
// 解析/格式化器
DateTimeFormatter dtf1=DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss EE a");
// 格式化
System.out.println(dtf1.format(time));  //将时间转化为字符串格式
```
## Localdate
- `LocalDate` 是一个不可变的日期时间对象，表示日期，通常被视为年 - 月 - 日。还可以访问其他日期字段，例如日期，星期几和星期。例如，值“2007 年 10 月 2 日”可以存储在 `LocalDate` 。
### 获取 localdate 对象
```java
    LocalDate nowDate = LocalDate.now();
    System.out.println("今天的日期:" + nowDate);  //直接就是年月日 ,不用在进行格式化转换了
    //2.获取指定的时间的日历对象
    LocalDate ldDate = LocalDate.of(2023, 1, 1); //获取指定的年月日
    System.out.println("指定日期:" + ldDate);
```
### get 系列获取日历中每一个属性值
```java
    //3.get系列方法获取日历中的每一个属性值//获取年
    int year = ldDate.getYear();
    System.out.println("year: " + year);
    //获取月//方式一:
    Month m = ldDate.getMonth();  //有一个类是Month类,内部定义了0-11个月的常量
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

```
### 判断日期的前后
```java
    //is开头的方法表示判断
    System.out.println(ldDate.isBefore(ldDate));
    System.out.println(ldDate.isAfter(ldDate));
```
### 修改日期
```java
    //with开头的方法表示修改，只能修改年月日
    LocalDate withLocalDate = ldDate.withYear(2000);
    System.out.println(withLocalDate);

    //minus开头的方法表示减少，只能减少年月日
    LocalDate minusLocalDate = ldDate.minusYears(1);
    System.out.println(minusLocalDate);


    //plus开头的方法表示增加，只能增加年月日
    LocalDate plusLocalDate = ldDate.plusDays(1);
    System.out.println(plusLocalDate);
```
### 常见用处, 判断生日
- `MonthDay`是一个不可变的日期时间对象，表示月份和日期的组合。 可以获得可以从一个月和一天获得的任何字段，例如四分之一年。
```java
    //-------------
    // 判断今天是否是你的生日
    LocalDate birDate = LocalDate.of(2000, 1, 1);
    LocalDate nowDate1 = LocalDate.now();

    MonthDay birMd = MonthDay.of(birDate.getMonthValue(), birDate.getDayOfMonth());
    MonthDay nowMd = MonthDay.from(nowDate1);

    System.out.println("今天是你的生日吗? " + birMd.equals(nowMd));//今天是你的生日吗?
```
## LocalTime
与这个 localdate 不同,localdate 获取的是年月日,localtime 获取的是时分秒
### 获取时间对象
```java
// 获取本地时间的日历对象。(包含 时分秒)
LocalTime nowTime = LocalTime.now();
System.out.println("今天的时间:" + nowTime);
System.out.println(LocalTime.of(8, 20));//时分
System.out.println(LocalTime.of(8, 20, 30));//时分秒
System.out.println(LocalTime.of(8, 20, 30, 150));//时分秒纳秒
LocalTime mTime = LocalTime.of(8, 20, 30, 150);

输出如下:
今天的时间:20:50:43.292645300
08:20
08:20:30
08:20:30.000000150
08:20:30.000000150

```

### 获取时分秒
```java
int hour = nowTime.getHour();//时
System.out.println("hour: " + hour);
int minute = nowTime.getMinute();//分
System.out.println("minute: " + minute);
int second = nowTime.getSecond();//秒
System.out.println("second:" + second);
int nano = nowTime.getNano();//纳秒
System.out.println("nano:" + nano);
```

### 判断方法
```java
//is系列的方法
System.out.println(nowTime.isBefore(mTime));
System.out.println(nowTime.isAfter(mTime));
```
### 修改方法
```java
//with系列的方法，只能修改时、分、秒
System.out.println(nowTime.withHour(10));
//plus系列的方法，只能修改时、分、秒
System.out.println(nowTime.plusHours(10));
```

## LocalDateTime  年、月、日、时、分、秒
这个是 localDate 和 localTime 的综合体
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
## 小结
在 Java 中，ZoneID、Instant、ZonedDateTime 和 DateTimeFormatter 这些类和接口用于处理日期、时间和时区相关的操作。下面是它们各自的功能说明：
1. ZoneID：ZoneID 类表示一个特定的时区。它提供了访问和操作时区的方法，比如获取可用的时区列表、根据时区 ID 获取时区对象等。
2. Instant：Instant 类代表从 1970 年 1 月 1 日00:00:00（格林威治时间）开始经过的时间（以秒为单位）。它用于处理瞬时时间点，可以用来进行时间戳的转换、计算时间间隔等。
3. ZonedDateTime：ZonedDateTime 类是在 Instant 的基础上加入了时区信息的日期时间表示。它包含了日期、时间和时区，并支持对日期时间的各种操作，比如获取年、月、日、时、分、秒等，以及转换时区、计算时间差等。
4. DateTimeFormatter：DateTimeFormatter 类可以用来格式化和解析日期时间字符串。它提供了一系列预定义的格式模式，也支持自定义格式。可以使用 DateTimeFormatter 将日期时间对象格式化为字符串，或者将字符串解析为日期时间对象。
综合来说，ZoneID 用于管理时区，Instant 用于处理瞬时时间点，ZonedDateTime 用于处理具有时区信息的日期时间，而 DateTimeFormatter 用于格式化和解析日期时间字符串。
Date 获取只能获取年月日, TIme 只能获取时分秒

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162234048.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307162235095.png)


## 时间间隔
### Duration（秒，纳，秒）
顾名思义就是获取两者之间的间隔, 最常用的方法是 between 方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202053225.png)
between 方法传递的参数是一个接口这个接口的实现类如下
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202054518.png)

**测试代码**
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

### Period 年月日
和这个 Durating 不同的是, 这个是用来计算间隔的年月日的,Duration 是用来计算时分秒的
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309202057071.png)

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
可以获取所有的单位
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
