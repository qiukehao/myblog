---
{"dg-publish":true,"permalink":"/02java//idea/","dgPassFrontmatter":true}
---

# IDEA中相对路径提示报错的原因

## 错误情况

今天在学习java的时候,学到了这个IO流,因为要使用这个文件的路径来创建对象,所以不可避免的接触到了这个路径问题.

当使用下面的代码的时候系统出现了错误,提示

```java
OutputStream os = new FileOutputStream("summary_study\\src\\file\\fileStream\\output.txt",true);
```

![image-20230805192849165](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308051928221.png)



此时我的包目录是

![image-20230805192921603](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308051929635.png)



## 原因

我们在面对这种情况的时候,错误原因很容易就可以得到,就是自己的相对路径写错了,为什么这种写法会写错才是我接下来要说明的点

**首先我们要明白这个IDEA中的相对路径相对的是什么东西**

经过查询资料发现,这个IDEA相对的路径是本项目的路径也就是这个分红色方框圈着的目录

![image-20230805193212245](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308051932275.png)

路径是相对与这个路径来说的 所以我们在从绝对路径变化为相对路径的时候只需要把这个路径给去掉就是相对路径了

```
绝对路径
D:\code\javaidea\summary_study\src\file\fileStream\output.txt
相对路径是绝对路径减去下面的路径
D:\code\javaidea\summary_study\
也就是
src\file\fileStream\output.txt
```

参考博客

[关于IDEA中写相对路径时，报错（系统找不到指定的路径](https://blog.csdn.net/weixin_49864248/article/details/119003994)