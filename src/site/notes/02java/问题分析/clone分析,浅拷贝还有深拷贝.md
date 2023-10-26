---
{"dg-publish":true,"permalink":"/02java//clone/","dgPassFrontmatter":true}
---

在Java中，clone()方法用于创建一个对象的拷贝。要使用clone()方法，需要满足以下条件：

被克隆的类必须实现Cloneable接口，该接口是一个标记接口，表示该类支持克隆操作。

在被克隆类中，需要重写Object类中的clone()方法，并将其访问修饰符设置为public。

下面是一个示例代码，演示如何使用clone()方法来创建一个对象的拷贝：

```java
class Person implements Cloneable {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 重写clone()方法
    @Override
    public Object clone() throws CloneNotSupportedException {
	    Person cloned = (Person)super.clone(); //简单的clone只是浅拷贝
	    cloned.name = (String)name.clone();  //对于这个引用变量我们进行深拷贝
        return cloned;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person("Alice", 25);

        try {
            // 使用clone()方法克隆对象
            Person person2 = (Person) person1.clone();

            System.out.println("person1: " + person1.getName() + ", " + person1.getAge());
            System.out.println("person2: " + person2.getName() + ", " + person2.getAge());
        } catch (CloneNotSupportedException e) {
            e.printStackTrace();
        }
    }
}
```
在上述代码中，我们定义了一个Person类，它实现了Cloneable接口并重写了clone()方法。在main()方法中，我们创建了一个Person对象person1，然后使用clone()方法创建了一个拷贝对象person2。最后，通过打印两个对象的属性，可以看到它们是完全独立的，修改其中一个对象不会影响另一个对象。

需要注意的是，clone()方法是浅拷贝（shallow copy），即只复制对象本身和其内部基本类型成员变量的值。如果被克隆的对象包含其他引用类型的成员变量，那么这些成员变量会共享同一个对象，需要根据实际需求进行深拷贝（deep copy）。



```java
    @Override
    public Object clone() throws CloneNotSupportedException{
        return super.clone();
    }这里的throws CloneNotSupportedException作用是什么
```

为什么会有重写呢,因为我们查看这个clone的源码可以知道这个clone函数是个proteced类型的
并且我们发现这个并没有写返回值,所以我们要对这个方法进行重写,让其能够进行返回

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202307112002016.png)


```
在 clone() 方法的定义中，throws CloneNotSupportedException 用于声明该方法可能抛出 CloneNotSupportedException 异常。这是因为 clone() 方法是 Object 类中的一个受保护的方法，当被克隆的类没有实现 Cloneable 接口时，调用 clone() 方法会抛出 CloneNotSupportedException 异常。

CloneNotSupportedException 是一个受检异常，需要在方法签名中进行声明。如果调用者希望使用 clone() 方法对特定对象进行克隆，就需要在代码中捕获或继续抛出该异常。

在示例代码中，我们在 clone() 方法的声明中抛出了 CloneNotSupportedException 异常。这意味着，如果 Person 类没有实现 Cloneable 接口，那么在调用 person1.clone() 时就会抛出该异常。如果在调用处没有捕获该异常或使用 throws 继续向上抛出，那么程序就会报编译错误。

简而言之，throws CloneNotSupportedException 的作用是告诉调用者：如果被克隆的对象所属类没有正确地实现 Cloneable 接口，或者没有重写 clone() 方法，那么调用 clone() 方法会导致 CloneNotSupportedException 异常的抛出，需要在代码中进行处理。
```