---
{"dg-publish":true,"permalink":"/02java///idea/","dgPassFrontmatter":true}
---

# 层级介绍
## 结构分类 

* project（项目、工程）
* module（模块）
* package（包）
* class（类）

## 结构介绍 

为了让大家更好的吸收，package这一层级，我们后面再学习，先学习最基础的project、module、class。


### project（项目、工程）

淘宝、京东、黑马程序员网站都属于一个个项目，IDEA中就是一个个的Project。

[名字](obsidian://open?vault=obsidian%E8%B5%84%E6%96%99&file=%E7%99%BD%E6%9D%BF%2F%E5%A4%A7%E4%BA%8C%E4%B8%8B%E6%9C%9F%E6%9C%AB%E8%80%83%E8%AF%95%E5%A4%8D%E4%B9%A0%2F%E7%A6%BB%E6%95%A3%E6%95%B0%E5%AD%A6)

### module（模块）

在一个项目中，可以存放多个模块，不同的模块可以存放项目中不同的业务功能代码。在黑马程序员的官方网站中，至少包含了以下模块：

* 论坛模块
* 报名、咨询模块

为了更好的管理代码，我们会把代码分别放在两个模块中存放。


### package（包）

一个模块中又有很多的业务，以黑马程序员官方网站的论坛模块为例，至少包含了以下不同的业务。

* 发帖
* 评论

为了把这些业务区分的更加清楚，就会用包来管理这些不同的业务。


### class（类）

就是真正写代码的地方。

## 小结

* 层级关系
* project - module - package - class
* 包含数量
* project中可以创建多个module ​ module中可以创建多个package ​ package中可以创建多个class
* 这些结构的划分，是为了方便管理类文件的。

# 快捷键

alt 加 insert 可以快速构建javaBean类型
alt加enter可以快速看错误提示信息
ctrl p 可以看这个函数有什么参数
souf可以快速输出这个输出函数
psvm可以快速打印main函数
ctrl 加alt 加t我们可以进行包裹我们选中的代码
ctrl加alt加v是自动生成 前面的对象
我们可以直接写方法名字,然后按住alt加回车,可以快速生成方法名
alt加shft加方向键可以快速进行行与行的交换
shift+F6多选，批量修改
ctrl+shift+u字符串转化为大写
ctrl+alt+m可以根据我们的代码块快速生成函数
ctrl+w快速选中当前单词
ctrl+alt+t对选中的代码进行添加这个判断,循环,trlcatch语句
# 自我总结
我们能不把这个数据写死就不要写死
数据的System.out.println()我们如果要进行变量的运算的话,我们可以加个小括号就行了