---
{"dg-publish":true,"permalink":"/02java//public-static-void-main-string-args-args/","dgPassFrontmatter":true}
---

## 重新认识 main 方法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202304111558662.png)



要向 `public static void main(String[] args)` 中的 `args` 数组传递参数，可以在命令行中运行 Java 程序时附加参数。

以下是两种常见的方法：

1. 在命令行中手动输入参数：
   
   我们首先要进入这个类所在的文件夹
   
   在命令提示符或终端中输入类似以下格式的命令来运行 Java 程序：
   
   ```
   java YourClassName arg1 arg2 arg3 ...
   ```
   其中 `YourClassName` 是你要执行的 Java 类的名称，后面的 `arg1`、`arg2`、`arg3` 等等是你要传递给 `main` 方法的参数。
   
   **注意点**
   
   这个命令行执行java类,是不支持中文的.所以你的代码中不要包含中文
   
   
   
2. 在集成开发环境（IDE）中配置参数：
   如果你使用的是集成开发环境（如 Eclipse、IntelliJ IDEA 等），可以在相应的配置中设置参数。
   
   - 在 Eclipse 中：右键单击项目，选择 "Run As" -> "Run Configurations"，然后在 "Arguments" 选项卡中填写需要的参数。
   - 在 IntelliJ IDEA 中：点击顶部菜单中的 "Run" -> "Edit Configurations"，然后在 "Program arguments" 输入框中添加参数。

无论你选择哪种方法，参数都将作为字符串存储在 `args` 数组中，可以在程序中使用。

```java
public class test {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            String arg = args[i];
            if (arg.equals("-h")) {
                arg = "hellp";
            } else if (arg.equals("-g")) {
                arg = "Goodbye";
            }
            System.out.println(arg);
        }
    }
}
Goodbye
cruel
world
```

