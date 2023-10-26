---
{"dg-publish":true,"permalink":"/06/css/","dgPassFrontmatter":true}
---

# CSS
## 1.0  css初始和基本选择器
### 1.1 基础认知

css中文名是层叠样式表，是用来给web网页做装饰的一种代码语言

> 怎么写

通过选择器来进行引入,每一个样式写完后都要有分号

• 只有一个语法
	选择器{
			声明1；
			声明2；
			声明3；
	}
• 难的是声明
• 每个声明由一个属性一个值组成，属性是您希望设置的样式属性，每个属性有一个值，属性和值被冒号分开
• 声明总是以分号结束，声明总以大括号{}括起来
• css的优势
	○ 内容和表现分离
	○ 网页结构表现同意，可以实现复用
	○ 样式十分的丰富
	○ 建议使用独立于html的css文件
	○ 利用SEO，容易被搜索引擎收录！
VUE用的话不容易被搜索器搜索。


### 1.2 css的引入方式
> 内联式

写在html文件里面用style标签进行书写style标签一般写在head里面,title下面
这种的css属性只能作用在当前页面,且不符合web标准的三层分离

```html
<style>
选择器{
属性名: 属性值;
属性名: 属性值;
属性名: 属性值;
}
</style>
```

>外联式

利用link来引入,将样式文件单独写在css文件中,这种样式可以作用于多个页面,只需要用link属性来进行链接就好

> 行内式

写在标签里面的style属性中,作用范围是当前表掐灭,不符合web标准的三层分离,此时的分号也是有的


	<p style="color: green;"> </p>


> 常见的属性
- color改变颜色
- font-size改变大小
- background-color背景颜色
- width 宽度
- height 高度

### 1.3 标签选择器
结构: 
标签名{
	css属性值:属性值;
	css属性值:属性值;
	css属性值:属性值;
}

作用:
通过标签名,找到页面中所有这类标签设置样式
注意点:
- 标签选择器选择的是一类标签,并非单独的某一个
- 无论标签嵌套的有多深,都能找到对应的标签


### 1.4 类选择器
> 结构: 

点加类名{
css属性值:属性值;
css属性值:属性值;
css属性值:属性值;
}

> 作用:

通过类名,找到页面中所有带有这个类名的标签

> 注意点:

1. 所有标签上都有class属性，class属性的属性值称为类名〈类似于名字)
2. 类名可以由数字、字母、下划线、中划线组成，但不能以数字或者中划线开头
3. 一个标签可以同时有多个类名类名之间以空格隔开
4. 类名可以重复--几个标签可以 有相同的类名，一个类选择器可以同时选中多个标签

### 1.5 id选择器
> 结构

井号加属性值{
css属性值:属性值;
css属性值:属性值;
css属性值:属性值;
}

> 作用

通过id属性值,找到页面中带有这个id属性值的标签,设置样式

> 注意点

1. 所有标签上都有id属性
2. id属性值类似于身份证号码，在一个页面中是唯一的，不可重复的!,class属性名是可以重复的,不同的标签值可以有相同的class属性
3. 一个标签上只能有一个id属性值
4. 一个id选择器只能选中一个标签

### 1.6 class和id的区别

> class类名与id属性名的区别

class类名相当于姓名，可以重复，一个标签可以同时有多个class类名. id属性值相当于身份证号码，不可重复，一个标签只能有一个id属性值

>类选择器与id选择器的区别

1. 类选择器以.开头
2. id选择器以#开头实际开发的情况
3. 类选择器用的最多
4. id一般般配合js使用，除非特殊情况，否则不要使用id设置样式
5. 实际开发中会遇到冗余代码的抽取（可以将一些公共的代码抽取到一个公共的类中去)

### 1.7 通配符选择器
> 结构

```html
* {   // 中间有空格的
css属性值:属性值;
}
```

对页面中多有的标签,设置样式
注意点是:
- 开发中使用极少,只会在极特殊情况下才会用到
- 在某些小页面中可能会用于去除标签默认的margin和padding


## 2.0 font字体

### 2.1 字体和文本样式
> 字体大小

1. font-size属性设置文本的大小
2. 字体大小分为绝对大小和相对大小
	a. 绝对大小
		1. 设置一个指定大小的文本
		2. 不允许用户在所有浏览器中改变文本大小
		3. 确定了输出的物理尺寸时绝对大小很有用
	b. 相对大小
		1. 相对于周围的元素来设置大小
		2. 允许用户在浏览器中改变文字大小
3. 我们现在经常用em来进行调整文本的大小，1em的默认大小是1px
4. 如果我们想改变系统字体的默认大小我们可以在body中设置百分比body {font-size:100%;}
**注意点**
谷歌浏览器默认字体大小是16px
单位需要设置,否则无效

### 2.2 字体粗细

> 字体粗细

属性名: font-weight
	○ font-weight:normal;，正常粗细 字体粗细的默认值,可以不设置
	○ font-weight:lighter;，细一点
	○ font-weight:bold;，粗一点(加粗)
	○ font-weight:900;，我们可以直接设置字体的粗细
		400是默认,700是加粗,根据这两个标准进行调整
		调整范围是400-900
**注意点**
- 不是所有字体都提供了九种粗细,因此部分取值页面中无变化
- 实际开发中,以正常,加粗两种取值用的最多


### 2.3 字体样式
> 字体样式

1. 正常font-style:normal   默认值,写不写都是这个效果
2. 斜体font-style:italic; 
3. 倾斜的文字-文字向一边倾斜（和斜体非常类似，但不太支持）font-style:oblique;

### 2.4 常见的字体系列

> 字体系列
- 无衬线字体(sans-serif)
1. 特点:文字笔画粗细均匀，并且首尾无装饰
2. 场景:网页中大多采用无衬线字体
3. 常见该系列字体:黑体、Arial
- 衬线字体(serif)
1. 特点:文字笔画粗细不均，并且首尾有笔锋装饰
2. 场景:报刊书籍中应用广泛
3. 常见该系列字体:宋体、Times New Roman
- 等宽字体(monospace)
1. 特点:每个字母或文字的宽度相等
2. 场景:一般用于程序代码编写，有利于代码的阅读和
3. 常见该系列字体:Consolas、fira code

> 设置方法

常见取值: 具体字体1,具体字体2,具体字体3...字体系列
从左到右按照顺序查找,如果电脑中未安装该字体,则显示下一个字体
如果都不支持，此时会根据操作系统，显示最后字体系列的默认字体

1. font-family属性应该设置几个字体名称作为一种后备机制，如果浏览器不支持第一种字体，他将尝试下一种字体，
```html
p {
font-family : 隶书,楷体,宋体,sans-serif;
}
```
3. 系统的默认字体,就是浏览器的默认字体
4. 多个字体系列是用一个逗号隔开的
**注意点**
如果字体系列的名称超过一个单词并且中间使用空格分开的，它要用单引号给圈着
最后一项字体系列不需要引号包裹
网页开发是,尽量使用系统常见的自带字体,保证不同用户浏览网页都能正常显示

### 2.5 字体的转变
1. font-variant：small-caps，所有的小写字母均会被转化为大写，并且小写字母转换到大写字母的字体样式和正常的大写字母的样式不同
我们可以在一个声明中声明所有的字体属性

### 2.6 样式的层叠问题

>问题:

给同一个标签设置了相同的样式，此时浏览器会如何渲染呢?
>结果:

如果给同一个标签设置了相同的属性，此时样式会层叠（覆盖)，写在最下面的会生效

>TIP:

- css (Cascading style sheets)层叠样式表
- 所谓的层叠即叠加的意思，表示样式可以一层一层的层叠覆盖

### 2.7 字体font相关属性的连写

属性名: 
font
取值:
font : style weight size family;
顺序要求:
swsf(稍微舒服)》 顺序不能变化,否则没有效果
省略要求:
只能省略前两个，如果省略了相当于设置了默认值
注意点:
如果需要同时设置单独和连写形式
要么把单独的样式写在连写的下面---因为写在上面的时候下面会重新赋给默认值给其覆盖点,
要么把单独的样式写在连写的里面,就是正常连写


## 3.0 文本样式

### 3.1 文本缩进
> 方法 text-indent属性

方法一:
```html
	p {
		text-indent: 32px;
	}
```
此时由于浏览器的默认字体是16px所以32px是缩进两个字符,但是不推荐使用这种方法,因为浏览器的字体大小并不是一成不变的,我们是要修改的,所以我们一般用相对大小
方法二:
```html
	p {
		text-indent: 2em;
	}
```
1em的大小是当前标签的一个字符font-size的大小,我们这里就是直接缩进了两个字符大小

### 3.2 文本的水平对齐方式
> 属性名
text-align

> 属性值
right，left，center

这种对齐一般都要设置一个盒子,要有一个参考才能更好的看出对齐效果

```html
.box {
		width: 400px;
		height: 400px;
		background-color: skyblue;
		text-align: center;
	}
<div class="box">
        我是一行文本
</div>        
```

文本的对齐方式
	1. center，right，left这些是最普通的对齐方式，就是字面的意义
	2. justify两端对齐，为了让文字的两端和占据的区域两端对齐，调整一定的文本间距

### 3.3 文本修饰
text-decoration underline是下划线，line-through中划线，overline上划线，none无划线
```html
text-decoration: underline;
text-decoration: line-through;
text-decoration: overline;
text-decoration: none;
```
**其中underline和none是最常用的,none可以用来消除链接标签的下划线**

### 3.4 水平居中的方法总结

> text-align :center

text-align可以让什么元素居中
- 文本
- span标签,a标签
- input标签,img标签

**如果需要让以上元素水平居中,text-align center需要给以上元素的父元素设置**

```html
.box {
		width: 400px;
		height: 400px;
		background-color: skyblue;
		text-align: center;
		text-decoration: underline;
	}
<div class="box">
        我是一行文本
        <br><br>
        <span>wo ai ni</span>
        <br><br>
        <input type="text">
        <br><br>
        <img src="../day2/images/logo_baidu.jpg" alt="dd">
        <br><br>
    </div>
```

### 3.5水平居中的方法2

```css
.father {
            width: 400px;
            height: 400px;
            background-color: skyblue;
            margin: 0 auto;
        }
        .son {
            width: 40px;
            height: 40px;
            background-color: red;
            margin: 0 auto;
        }
```
```html
<div class="father">
	<div class="son">
	</div>
</div>
```

如果需要让div,p,h这种的大盒子水平居中的话,是不能用text-align属性的,不信的话可以设置两个div验证一下

我们可以利用magin: 0 auto;来实现大盒子的水平居中效果
大盒子本身的水平居中是相对网页的水平居中,大盒子内部嵌套的小盒子的水平居中是相对大盒子的水平居中

**注意点**
magin: 0 auto; 一般针对固定宽度的盒子,如果大盒子没有设置宽度,此时会默认占满父元素的宽度,没有居中的意义

### 3.6 文本高度

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301041646886.png)


line-height指定一个文本的行高，行高和盒子的高度相同的时候就是可以让元素在盒子中处于上下居中状态

行高的作用是控制行间距,给一行文字或者其他元素增加间距
属性名line-height
取值: 
- 数字加px
- 倍数(当前标签 font-size的倍数)
应用:
1. 让单行文本垂直居中可以设置line-height:文字父元素高度
2. 网页精准布局时:会设置line-height=1;可以取消上下间距

### 3.7 行高和font的覆盖问题
**注意点**
- 如果同时设置了行高和font连写,注意覆盖问题,line-height应该放在font连写的下面,否则会被覆盖
- font:style weight size/line-height family;
line-height应该写在size后面中间用/隔开



### 3.8 文本转换
1. text-transform：uppercase，所有的字母都大写
2. text-transform：lowercase，所有的字母都小写
3. text-transform：capitalize，所有的字母都首字母大写



## 4.0 chrome的调试工具
> 打开方式

- 右击检查
- 看哪里,点哪里,点代码,和点页面元素都可以

> 控制样式

- 修改属性值
在右边的框子中的style框中,选择代码直接修改
对于一些数字属性,我们可以直接利用滚轮拖动进行修改

- 添加属性
回车就可以添加样式了
如果修改的样式比较满意,记得保存

- 控制样式生效
对于样式而言,可以点击前面的小方块来控制该行代码是否生效

> 特殊情况

个别属性出现了删除线,但是前面的选择框是勾选的状态,这种情况,一般是因为后面有重复的,把这个属性给覆盖掉了

对于注释的代码来说,style控制台中仍然会显示,但是此时是有删除线的,我们可以重新勾选上

属性中出现了三角感叹号,这种情况是你的代码出错了
- 分号没写
- 中文分号
- 属性名错了
鼠标放置后会出现错误提示

> computed那里可以查找属性值

## 小案例
### 案例一: 自然杂志的制作
> 收获
- 只出现一次的标签,例如h1这种大标题,我们直接用标签选择器就好了
- 相同类型的标签,我们要学会用div给圈出来

```css
.box {
    width: 800px;
    /* height: 800px; */
    /* background-color: yellow; */
    margin: 0 auto;
}
.title {
    text-align: center;
}
.info {
    text-align: center;
}
.date {
    color: grey;
}
.company {
    color: skyblue;
    font-weight: bold;
}
a {
    text-decoration: none;
}
.paragraph {
    text-indent: 2em;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./自然.css">
</head>
<body>
    <div class="box">
        <h1 class="title">《自然》评选改变科学的10个计算机代码项目</h1>

        <div class="info">
            <span class="date">2077年01月28日14:58</span>
            <span class="company">新浪科技</span>
            <span> <a href="#">收藏本文</a></span>
        </div>
    
        <hr>
        
        <div class="paragraph">
            <p>2019年，事件视界望远镜团队让世界首次看到了黑洞的样子。不过，研究人员公布的这张发光环形物体的图像并不是传统的图片，而是经过计算获得的。利用位于美国、墨西哥、智利、西班牙和南极地区的射电望远镜所得到的数据，研究人员进行了数学转换，最终合成了这张标志性的图片。研究团队还发布了实现这一壮举所用的编程代码，并撰文记录这一发现，其他研究者也可以在此基础上进一步加以分析。</p>
            <p>这种模式正变得越来越普遍。从天文学到动物学，在现代每一项重大科学发现的背后，都有计算机的参与。美国斯坦福大学的计算生物学家迈克尔·莱维特因“为复杂化学系统创造了多尺度模型”与另两位研究者分享了2013年诺贝尔化学奖，他指出，今天的笔记本电脑内存和时钟速度是他在1967年开始获奖工作时实验室制造的计算机的1万倍。“我们今天确实拥有相当可观的计算能力，”他说，“问题在于，我们仍然需要思考。”</p>
            <p>如果没有能够解决研究问题的软件，以及知道如何编写并使用软件的研究人员，一台计算机无论再强大，也是毫无用处的。如今的科学研究从根本上已经与计算机软件联系在一起，后者已经渗透到研究工作的各个方面。近日，《自然》（Nature）杂志将目光投向了幕后，着眼于过去几十年来改变科学研究的关键计算机代码，并列出了其中10个关键的计算机项目。</p>
            <p>最初的现代计算机并不容易操作。当时的编程实际上是手工将电线连接成一排排电路来实现的。后来出现了机器语言和汇编语言，允许用户用代码为计算机编程，但这两种语言都需要对计算机的架构有深入的了解，使得许多科学家难以掌握。20世纪50年代，随着符号语言的发展，特别是由约翰·巴克斯及其团队在加州圣何塞的IBM开发的“公式翻译”语言Fortran，这种情况发生了变化。利用Fortran，用户可以用人类可读的指令来编程，例如x = 3 + 5。然后由编译器将这些指令转换成快速、高效的机器代码。</p>
        </div>
    </div>
</body>
</html>
```

> 最终效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301041827543.png)


### 案例二: 小米官网图片卡片样例
> 总结
- 文本的放置用div也可以起到p的换行效果,且用div的位置更好摆放,适用于小段且位置特殊的文字
- 盒子高度事盒子高度height,文本高度事文本高度line-height,这两个事不一样,文本默认在盒子的上方对齐

```css
body {
    background-color: #f5f5f5;
}
.box {
    width: 234px;
    height: 300px;
    background-color: #fff;
    margin: 0 auto;
    text-align: center;
}
img {
    width: 160px;
}
.jiuhao {
    font-size: 14px;
    height: 25px;
}
.toy {
    font-size: 12px;
    /* line-height: 30px; */
    color: #cccccc;
    height: 30px;
}
.price {
    font-size: 14px;
    color: #ffa500;
}
```



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./卡片.css">
</head>
<body>
    <div class="box">  
        <img src="./car.jpg" alt="平衡车">
        <div>
            <div class="jiuhao">九号平衡车</div>
            <div class="toy">成年人的玩具</div>
            <div class="price">1999元</div>
        </div>
    </div>
</body>
</html>
```


> 最终效果

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051105077.png)

### 案例三: 新闻页面
> 收获

1. p里面的文字除了特别修饰的用span圈起来,其他的文字直接写就好
2. 在注重层次结构的时候,我们要注意回车等于一个空格


>效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051232994.png)


```css
.box {
    text-align: center;
}
h1 {
    /* color: #000000;
    font-size: 32px; */
    font-weight: 400;
}
h4 {
    font-size: 20px;
    text-align: center;
}
.time {
    color: #888888;
    font-size: 12px;
}
a {
    text-decoration: none;
    color: #551A8B;
    font-size: 12px;
}
p {
    text-indent: 2em;
}
.source {
    color: #888888;
    font-size: 12px;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>中国天气网</title>
    <link rel="stylesheet" href="./news.css">
</head>
<body>
    <div class="box">
        <h1>北方高温明日达鼎盛 京津冀多地地表温度将超60℃</h1>
        <span class="time">2021-5-25 18:31:47 来源: </span>
        <a href="#">中国天气网&nbsp;&nbsp;&nbsp;</a>
        <input type="text" placeholder="请输入查询条件">
        <button type="submit">搜索</button>
    </div>

    <hr>

    <p>中国天气网讯：今天（25日），华北、黄淮多地出现高温天气，截至下午2点，北京、天津、郑州等地气温突破35℃。预报显示，今后三天（25-28日），这一带的高温天气将继续发酵，高温范围以及强度将在29日达到鼎盛，预计北京、天津、石家庄、济南等地明天的最高气温有望突破38℃，其中北京和石家庄的最高气温还有望创今年以来的新高。</p>  
    
    <h4>气温41.4℃！地温66.5！北京强势迎七月首个高温日</h4>

    <div class="box">
      <img src="./pic.jpeg">
    </div>

    <p>今天，华北、黄淮一带的高温持续发酵，截至今天下午2点，陕西北部、山西西南部、河北南部、北京、天津、山东西部、河南北部最高气温已普遍超过35℃。大城市中，北京、天津、郑州均迎来高温日。在阳光暴晒下，地表温度也逐渐走高。今天下午2点，华北黄淮大部地区的地表温度都在50℃以上，部分地区地表温度甚至超过60℃。其中，河北衡水地表温度高达68.3℃，天津站和北京站附近的地表温度分别高达66.6℃和66.5℃。</p>
    <h4>明日热度再升级！京津冀携手冲击38℃+</h4>
    <p>中国天气网气象分析师王伟跃介绍，明天（26日），华北、黄淮地区35℃以上的高温天气还将继续升级，并进入鼎盛阶段，高温强度和范围都将发展到最强。 明天，北京南部、天津大部、河北中部和南部、山东中部和西部、山西南部局地、河南北部、东北部分地区的最高气温都将达到或超过35℃。</p>
    <p>不过，专家提醒，济南被雨水天气完美绕开，因此未来一周，当地的高温还会天天上岗。在此提醒当地居民注意防暑降温，防范持续高温带来的各种不利影响。（文/张慧 数据支持/王伟跃 胡啸 审核/刘文静 张方丽）</p>

    <p class="source">本文来源：中国天气网 责任编辑：刘京_NO6666</p>
</body>
</html>
```

### 案例四: 百度搜索页

> 效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051233815.png)

```css
.title {
    color: #2440b3;
    font-size: 18px;
}
span {
    color: #CC0000;
}
.paragraphs {
    font-size: 13px;
}
.website {
    color: #008800;
    font-size: 13px;
    text-decoration: none;
}
.image {
    color: #666666;
    font-size: 13px;
    text-decoration: none;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./百度.css">
</head>
<body>
    <div>
        <p>
            <a href="#" class="title">
                零基础开始学
                <span class="bigweb"> Web 前端</span>
                开发，有什么建议吗？-知乎
            </a>
        </p>
        
        <p class="paragraphs">
            <span class="smallweb">Web 前端</span>
            开发技术主要包括三个要素：HTML、CSS 和 JavaScript，它要求前端开发工程师不仅要掌握基本的Web 前端开发技术，网站性能优化，SEO 和服务器端的基础...
            <span class="smallweb">Web 前端</span>
        </p>

        <p>
            <a href="#" class="website">http://www.zhihu.com/question...</a>
            <img src="./v2.png">
            <a href="#" class="image">百度快照</a>
        </p>

        <p>
            <a href="#" class="title">
                <span class="bigweb"> Web 前端</span>
                技术论坛所有讨论帖 - ITeye论坛频道
            </a>
        </p>
        
        <p class="paragraphs">
            <span class="smallweb">Web 前端</span>
            技术版面讨论，JavaScript编程、AJAX开发、UI界面设计、CSS 分类: JavaScript AJAX EXT JQuery prototype CSS 界面设计...
        </p>

        <p>
            <a href="#" class="website">www.iteye.com/forums/b...</a>
            <img src="./v2.png">
            <a href="#" class="image">百度快照</a>
        </p>
    </div>
</body>
</html>
```

### 案例五: 百度首页

>效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051257818.png)

```css
.box {
    text-align: center;
}
a {
    color: #551a8b;
}
.web {
    text-decoration: none;
    color: #000000;
    font-weight: 700;
}
.link {
    height: 56px;
}
.search {
    height: 54px;
}
.search-box{
    width: 425px;
    height: 30px;
}
.button {
    width: 84px;
    height: 24px;
}
.more {
    height: 56px;
}

.map {
    height: 62px;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>baidu</title>
    <link rel="stylesheet" href="./百度首页.css">
</head>
<body>
    <div class="box">
        <img src="./logo.gif" alt="logo">
        <br>
        <div class="link">
            <a href="#">新 闻</a>
            <a href="#" class="web">网 页</a>
            <a href="#">贴 吧</a>
            <a href="#">知 道</a>
            <a href="#">音 乐</a>
            <a href="#">新 闻</a>
            <a href="#">视 频</a>
            <a href="#">地 图</a>
        </div>

        <div class="search">
            <input type="text" class="search-box">
            <input type="submit" value="百度一下" class="button">
        </div>

        <div class="more">
            <a href="#">百科</a>
            <a href="#">文库</a>
            <a href="#">hao123</a>
            |
            <a href="#">更多>></a>
        </div>

        <div class="map">
            <img src="./icon.jpg">
            <a href="#">百度地图带你吃喝玩乐，全心全意为人民服务</a>
        </div>

        <div>
            <a href="#">把百度设为主页</a>
            <a href="#">安装百度卫士</a>
        </div>

        <div>
            <a href="#">加入百度推广</a>
            |
            <a href="#">搜索风云榜</a>
            |
            <a href="#">关于百度</a>
            |
            <a href="#">About Baidu</a>
        </div>

        <p>©2021 Baidu 使用百度前必读 京ICP证030173号</p>

    </div>

</body>
</html>
```


## 5.0 css的颜色的常见取值
> 取值类型1：关键词

常见颜色取值：
- red：红色 
- green：绿色 
- blue：蓝色
- yellow：黄色
- orange：橘色
- skyblue：天蓝色 
- pink：粉色

> 取值类型2：rgb表示法

每项取值范围：0~255 
常见颜色取值：
- rgb ( 255 , 0 , 0 ) :   红色
- rgb ( 0 , 255 , 0 ) ：绿色 
- rgb ( 0 , 0 , 255 ) ：蓝色
- rgb ( 0 , 0 , 0 ) ：黑色 
- rgb ( 255 , 255 , 255 ) ：白色

> 取值类型3：rgba表示法 

比rgb表示法多个一个a，a表示透明度 
a的取值范围：0~1 • 
1：完全不透明 • 0：完全透明 
省略写法：
rgba ( 0 , 0 , 0 , 0.5 )可以省略写成 rgba ( 0 , 0 , 0 , .5 ) 其中0.5的0可以省略

> 取值类型4:  16进制表示法

取值范围：
**两个数字为一组**，每个数字的取值范围：0~9 , a , b , c , d , e , f 
省略写法： 
如果三组中，每组数字都相同，此时可以每组可以省略只写一个数字 
正确写法：#ffaabb 改写成 # fab
常见取值： # fff ：白色 #000 ：黑色
注意点 1
类似于：#ffaabc 不能改写成 # fabc 
实际开发中会直接使用测量工具直接得到颜色，不需要前端自己设计颜色，直接复制粘贴即可。

##  6.0 css复合选择器
### 6.1 后代选择器
- 后代选择器
    - 在某个元素的后面
    - 祖爷爷，爷爷，爸爸，你
    - body p{ };
> 作用

根据 HTML 标签的嵌套关系，选择父元素 后代中 满足条件的元素,当类选择器名字取太多了不好取名之后

> 编辑器语法

选择器1 选择器2 { css } 中间的空格一定不能少

> 结果

在选择器1所找到标签的后代（儿子、孙子、重孙子…）中，找到满足选择器2的标签，设置样式

> 注意点

1. 后代包括：儿子、孙子、重孙子…… 
2. 后代选择器中，选择器与选择器之前通过 空格 隔开

> 示例代码

```html
	<style>
        div p {
            color: red;
        }
        .father p {
            text-decoration: underline;
        }
    </style>
    <div class="father">
        <p>xiao shuai ge</p>
        <div> <p>xiao mei mei</p></div>
    </div>
    <p>xiao jie jie </p>
```

### 6.2 子代选择器

> 作用

根据 HTML 标签的嵌套关系，选择父元素 子代中 满足条件的元素

> 选择器的语法

选择器1 > 选择器2 { css }

> 结果

在选择器1所找到标签的子代（儿子）中，找到满足选择器2的标签，设置样式

> 注意点

1. 子代只包括：儿子 ,后代选择器是所有的后代,子代是只有儿子
2. 子代选择器中，选择器与选择器之前通过 > 隔开

> 示例代码

```html
<style>
	.father > p {
		color: violet;
	}
</style>
<div class="father">
	<p>xiao shuai ge</p>
	<div> <p>xiao mei mei</p></div>
</div>
```

### 6.3 并集选择器
> 作用

同时选择多组标签，设置相同的样式

> 选择器语法

选择器1 ，
选择器2 { css }

> 结果

找到 选择器1 和 选择器2 选中的标签，设置样式

> 注意点

1. 并集选择器中的每组选择器之间通过 , 分隔 
2. 并集选择器中的每组选择器可以是基础选择器或者复合选择器 
3. 并集选择器中的每组选择器通常一行写一个，提高代码的可读性
4. **并集选择器是指这些并列在一起的标签,并不代表这些标签的地位是相同的,即使是嵌套的也是可以用的**

> 示例代码

```html
<style>
	div,
	p ,
	.red {
		color: red;
	}
</style>
<div>wo</div>
<div>ai</div>
<p>ni</p>
<p>da</p>
<h1 class="red">mei</h1>
<h2>nv</h2>
<div class="father">
	<p>xiao shuai ge</p>
	<div> <p>xiao mei mei</p></div>
</div>
<p>xiao jie jie </p>
```

### 6.4 交集选择器
> 作用

选中页面中 同时满足 多个选择器的标签

> 选择器语法

选择器1选择器2 { css }  两个选择器要紧挨着才可以

> 结果

（既又原则）找到页面中 既 能被选择器1选中，又 能被选择器2选中的标签，设置样式

> 注意点

1. 交集选择器中的选择器之间是紧挨着的，没有东西分隔 
2. 交集选择器中如果有标签选择器，标签选择器必须写在最前面,不放在最前面,比如下面的示例中就是.redp这样的话就找不到red找不到p了

> 代码示例

```html
    <style>
        p.red{
            color: red;
        }
    </style>
    <div class="red">小姐姐</div>
    <p>小妹妹</p>
    <p class="red">御姐</p>    
```

### 6.5 总结
**四种组合方式**
	• 后代选择器（以空格分隔）
	• 子元素选择器 （以大于号分割）
	• 相邻兄弟选择器 （以加号+分割）
	• 普通兄弟选择器 （以波浪号分割）
**后代选择器**
```html
div p
{
	background-color:yellow;
}
< div>
< p>段落 1。 在 div 中。</p>
< p>段落 2。 在 div 中。</p>
</div>
后代选择器用于选取某元素的后代元素,以下实例选取div中所有的<p>元素 .
```
子元素选择器
```html
与后代选择器相比，子元素选择器（Child selectors）只能选择作为某元素直接/一级子元素的元素。
div>p
{
	background-color:yellow;
}
<div>
<h2>My name is Donald</h2>
<p>I live in Duckburg.</p>
</div>
<div>
<span><p>I will not be styled.</p></span>
</div>
上面的代码中只能选择第一个div中的p因为第一个是第一级,第二个中的p是第二级,前面还有一个span元素
```

**相邻兄弟选择器**
相邻兄弟选择器（Adjacent sibling selector）可选择紧接在另一元素后的元素，且二者有相同父元素。
```html
div+p
{
	background-color:yellow;
}
<di v>
<h2>DIV 内部标题</h2>
<p>DIV 内部段落。</p>
</div>
<p>DIV 之后的第一个 P 元素。</p>
<p>DIV 之后的第二个 P 元素。</p>
这串代码会选择的是<p>DIV 之后的第一个 P 元素。</p>因为他们的父元素相同,并且是紧挨着的
```

**后续兄弟选择器**
```html
后续兄弟选择器选取所有指定元素之后的相邻兄弟元素。
div~p
{
	background-color:yellow;
}
<p>之前段落，不会添加背景颜色。</p>
<div>
<p>段落 1。 在 div 中。</p>
<p>段落 2。 在 div 中。</p>
</div>
<p>段落 3。不在 div 中。</p>
<p>段落 4。不在 div 中。</p>
回旋曲div后面的所有相邻兄弟元素这个元素是~p已经指定了是p
```



## 7.0 emment语法

```html
    <!-- 生成普通标签: 标签选择器 div -->
    div加tab
    <div></div>
    <!-- 生成div标签+类名:类选择器.red -->
    .red
    <div class="red"></div>
    <!-- 生成div标签+id属性:id选择器 #one -->
    #one
    <div id="one"></div>
    <!-- 生成指定标签+类名+id属性: 交集选择器 p.red#one -->
    p.red#one
    <p class="red" id="one"></p>
    <!-- 生成儿子: 子代选择器ul > li -->
    div>p
    <div>
        <p></p>
    </div>
    <!-- 生成内部文本: 大括号 ul > li (我是li的内容) -->
    div{wo ai ni}
    <div>wo ai ni</div>
    <!-- 同时创建多个标签: *个数 ul>li *3 -->
    ul>li *3
    <ul>
        <li></li>
        <li></li>
        <li></li>
    </ul>
```

## 8.0 伪类选择器
### 8.1 hover伪类选择器
> 作用

选中鼠标悬停在元素上的状态，设置样式

> 语法

选择器:hover { css }          类似于并集选择器,需要同时满足悬停上去盒是这个选择器这两个条件,才会触发里面的css效果

> 注意点

伪类选择器选中的元素的某种状态

```html
    <style>
        a {
            text-decoration: none;
        }
        a:hover {
            color: yellow;
            text-decoration: underline;
        }
    </style>
    <a href="#">我爱你</a>    
```

### 8.2 结构伪类选择器
1. 作用：根据元素在HTML中的结构关系查找元素 
2. 优势：减少对于HTML中类的依赖，有利于保持代码整洁 
3. 场景：常用于查找某父级选择器中的子元素

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061632928.png)

它的书写格式是
E标签 :nth-child(n){

}
其中:nth-child(n)是一个部分,E标签是一个部分
它的作用匹配父元素中的第一个子元素,并且是E标签

比如说a:first-child{

} 的作用就是找到一个a元素,它有父元素,并且是父元素的第一个孩子,并将其选中

> 注意点

n默认为：0、1、2、3、4、5、6、……
如果不设置n的值,n就会自动遍历,直到遍历到不存在的标签

功能| 公式
偶数|2n,even
技术|2n+1,2n-1,odd
找到前5个|-n+5
找到从第五个往后|n+5

> 易错点

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061649755.png)

不能说是li a:first-child
这个的意思是找到li中的子元素a,看它是不是父元素的第一个元素,是的话就选中,这样的话就会选中多个

正确应该是li : first-child a
这个的意思是找到li,看它是不是父元素的第一个元素,是的话选中后,然后在选中它的孩子a

### 8.3 伪元素
> 一般页面中的非主题内容可以使用伪元素

元素:html设置的标签
伪元素：由 CSS 模拟出的标签效果
伪元素并不是存放到标签里,而是存放到父元素中的,它只是一个css模拟出来的标签效果

: : before 在父元素内容的最前面添加一个伪元素
: : after 在父元素内容的最后添加一个伪元素

**注意点**
1. 伪元素必须设置content属性才能生效
例如 content:'我是一个伪元素'
这个引号不能少
2. 伪元素默认是行内元素,不能直接设置宽和高,我们可以对其进行元素显示模式的转化display: block

### 8.4 链接伪类选择器
链接样式
	1. a:link - 正常，未访问过的链接的样式是什么样的
	2. a:visited - 用户已访问过的链接是什么样的
	3. a:hover - 当用户鼠标放在链接上时是什么样的
	4. a:active - 链接被点击的那一刻是什么样
	5. a:hover 必须在 a:link 和 a:visited 之后，需要严格按顺序才能看到效果。 a:active 必须在 a:hover 之后。

如果需要同时实现以上四种伪类状态效果，需要按照 LVHA 顺序书写
记忆口诀：男盆友送了你一个 LV 包包，你开心的 HA 哈笑
其中 :hover伪类选择器 使用更为频繁，常用于选择各类元素的悬停状态

### 8.5 焦点伪类选择器
> 场景:用于选中元素获取焦点时状态，常用于表单控件

>选择器语法:

	input:focus{
			background-color: blue;
	}


**效果：**
表单控件获取焦点时默认会显示外部轮廓线

### 8.6 属性选择器
通过元素上的HTML属性来选择元素，常用于选择 input 标签
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081225479.png)




## 9.0 css背景
### 9.1 背景颜色
> 属性名:

background-color（bgc）我们只需要输入bgc vscode就可以直接弹出来提示

>属性值：

颜色取值：关键字、rgb表示法、rgba表示法、十六进制……

> 注意点

- 背景颜色默认值是透明： rgba(0,0,0,0) 、transparent 是bgc的属性,代表透明,和 rgba(0,0,0,0)效果一样,全透明
- 背景颜色不会影响盒子大小，并且还能看清盒子的大小和位置，一般在布局中会习惯先给盒子设置背景颜色


### 9.2 背景图片
> 属性名

background-image（bgi）

> 属性值

background-image: url('图片的路径') 这个路径和之间的路径没什么区别,也是分为绝对路径和相对路径

> 注意点

- 背景图片中url中可以省略引号
- 背景图片默认是在水平和垂直方向平铺的
- 背景图片仅仅是指给盒子起到装饰效果，类似于背景颜色，是不能撑开盒子的,(盒子div的默认高度为0,如果直接向盒子里面添加图片,则盒子什么内容都显示不出来,必须要设置高度才可以)
### 9.3 背景平铺
1. 默认情况下背景图像进行平铺重复显示,以覆盖整个元素实体  默认就是是background-repeat:repeat
2. 如果想让图片在一个方向上进行平铺重复显示,我们可以用background-repeat:repeat x/y
3. 如果不想让图片进行重复显示,我们可以用background-repeat:no-repeat

### 9.4 背景的相关知识
> 属性名
改变图像的位置就是background-position

> 属性值
> background-position: 水平方向位置 垂直方向位置

> 取值
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301042206755.png)


> 注意点
- 方位名词和数字坐标可以昏庸,只要保持第一个取值表示水平,第二个表示垂直即可
- 数字坐标法,记住是图片的左上角于坐标点相重合

### 9.5 背景属性的连写
> 属性名
> background

> 写法是
- 单个属性值的合写，取值之间以空格隔开
- 推荐：background：color image repeat position

> 省略问题
- 可以按照需求省略
- • 特殊情况：在pc端，如果盒子大小和背景图片大小一样，此时可以直接写 background：url(),因为此时,背景图片已经把盒子给占满了,所以写其他的就没什么用了

> 注意点
- 写法的顺序是没有区别的,可以任意顺序,但是最好使用推荐顺序
- 连写的话我们就要考虑覆盖问题
 要么把单独的样式写在连写的下面;要么把单独的样式写在连写的里面

### 9.6 img标签和背景图片的区别
在网页中展示一张图片
方法一：直接写上img标签即可  img标签是一个标签，不设置宽高默认会以原尺寸显示
方法二：div标签 + 背景图片 必须需要设置div的宽高，因为背景图片只是装饰的CSS样式，不能撑开div标签

## 10.0 元素显示模式
### 10.1 块级元素
> 属性display：block

display是个属性值,块级元素的属性值是block

> 显示特点:
1. 独占一行（一行只能显示一个） 
2. **宽度默认是父元素的宽度**，高度默认由内容撑开 
3. 可以设置宽高

> 代表标签
- div、p、h系列、ul、li、dl、dt、dd、form、header、nav、footer……

### 10.2 行内元素

> 行内元素的display属性的属性值是?
    display：inline

> 行内元素的显示特点
1. 一行可以显示多个
2. 宽度和高度默认由内容撑开 
3. 不可以设置宽高, 设置了也没用

> 代表标签
- a、span 、b、u、i、s、strong、ins、em、del……


### 10.3 行内块元素
> 属性: display：inline-block

> 显示特点
1. 一行可以显示多个 
2. 可以设置宽高

> 代表标签
- input、textarea、button、select…… 
- 特殊情况：img标签有行内块元素特点，但是Chrome调试工具中显示结果是inline

### 10.4 元素显示模式的转换
> 目的

改变元素默认的显示特点，让元素符合布局要求

> 语法

display: block; 将元素转化为块级元素,让其独占一行,且可以设置宽和高  **常用**

display: inline-block; 将元素转化为行内块元素,让一行中可以放置多个可以设置宽和高的盒子  **常用**

display: inline; 将元素转化为行内元素  **很少用**

### 10.5 html的嵌套规范注意点

1. 块级元素一般作为大容器，可以嵌套：文本、块级元素、行内元素、行内块元素等等……
**但是**p标签中不要嵌套div、p、h等块级元素,如果代码中嵌套了,这是一种错误写法,浏览器会自动帮你进行修改,可能会导致你的错误
2. a标签内部可以嵌套任意元素
**但是**a标签不可以嵌套a标签,如果嵌套的话,浏览器会自动补齐代码,让这些a标签形成并列的关系


## 11.0 css的三大特性
### 11.1 继承性
> 特性

子元素有默认继承父元素样式的特点（子承父业）

>可以继承的常见属性：

1. color 
2. font-style、font-weight、font-size、font-family
3. text-indent、text-align 
4. line-height 
5. ……

> 注意点

- 可以通过调试工具判断样式是否可以继承
- 适用于那些需要相同css样式的元素,我们可以通过直接设置他们的父元素,来设置他们的样式
- 子承父业,然后孙承子业,

> 代码示例

```html
    <style>
        .father {
            color: red;
        }
    </style>
    <div class="father">
        父亲
        <div class="son">儿子
            <div class="grandson">孙子</div>
        </div>
    </div>
```

### 11.2 继承的应用
> 好处

可以在一定程度上减少代码

> 常见应用场景

1. 可以直接给ul设置 list-style:none 属性，从而去除列表默认的小圆点样式 
2. 直接给body标签设置统一的font-size，从而统一不同浏览器默认文字大小

### 11.3 继承失效的特殊情况
>如果元素有浏览器默认样式，此时继承性依然存在，但是优先显示浏览器的默认样式

> 常见失效

1. a标签的color会继承失效,其实color属性继承下来了，但是被浏览器默认设置的样式给覆盖掉了
2. h系列标签的font-size会继承失效,其实font-size属性继承下来了，但是被浏览器默认设置的样式给覆盖掉了
3. div的高度不能继承，但是宽度有类似于继承的效果,宽度属性不能继承，但是div有独占一行的特性,所以会产生类似于继承的效果

### 11.4 css层叠性
> 特点
1. 给同一个标签设置不同的样式 → 此时样式会层叠叠加 → 会共同作用在标签上 
2. 给同一个标签设置相同的样式 → 此时样式会层叠覆盖 → 最终写在最后的样式会生效
> 注意点
1. 当样式冲突时，只有当选择器优先级相同时，才能通过层叠性判断结果

### 11.5 css优先级

> 特性

不同选择器具有不同的优先级，优先级高的选择器样式会覆盖优先级低选择器样式

> 优先级公式

继承 < 通配符选择器 < 标签选择器 < 类选择器 < id选择器 < 行内样式 < !important
继承是子承父业的那个
通配符是对所有的元素设置样式

> 注意点

1. !important写在属性值的后面，分号的前面！
2. !important不能提升继承的优先级，只要是继承优先级最低！**继承优先级永远最低,无法改变**
3. 实际开发中不建议使用 !important 。

### 11.6 权重叠加计算
> 场景

如果是复合选择器，此时需要通过权重叠加计算方法，判断最终哪个选择器优先级最高会生效

> 权重叠加计算公式:(每一级之间不存在进位)
> 复合选择器中: 行内样式的个数;id选择器的个数;类选择器的个数;标签选择器的个数,依次列出

> 比较规则

1. 先比较第一级数字，如果比较出来了，之后的统统不看 
2. 如果第一级数字相同，此时再去比较第二级数字，如果比较出来了，之后的统统不看 
3. …… 不断重复上述操作
5. 如果最终所有数字都相同，表示优先级相同，则比较层叠性（谁写在下面，谁说了算!）

**注意点**：
1. !important如果不是继承，则权重最高，天下第一！
2. 先判断选择器是否能直接选中标签，如果不能直接选中 → 是继承，优先级最低 → 直接pass
3. 通过权重计算公式，判断谁权重最高
4. 实际开发中选择标签需要精准，尽量避免多个选择器同时选中一个标签的情况，不要自己难为自己
5. **交集选择器我们应该拆分来数,而不是将其看作一个**
6. 权重计算中对于父子关系的选择器和爷孙选择器,一般是关系越近权重越高




## 小案例

### 案例一: 普通导航
```css
a {
    display: inline-block;
    width: 80px;
    height: 50px;
    background-color: #FF0000;
    color: white;
    text-decoration: none;
    text-align: center;
    line-height: 50px;
}
a:hover {
    background-color: orange;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./普通导航.css">
</head>
<body>
    <div>
        <a href="#">导航1</a>
        <a href="#">导航2</a>
        <a href="#">导航3</a>
        <a href="#">导航4</a>
        <a href="#">导航5</a>
    </div>
</body>
</html>
```


### 案例二:  五彩导航案例

```css
a {
    display: inline-block;
    width: 120px;
    height: 58px;
    text-align: center;
    line-height: 50px;
    text-decoration: none;
    color: white;
}
.one {
    background-image: url('./images/bg1.png');
}
.two {
    background-image: url('./images/bg2.png');
}
.three {
    background-image: url('./images/bg3.png');
}
.four {
    background-image: url('./images/bg4.png');
}
.one:hover {
    background-image: url('./images/bg5.png');
}
.two:hover {
    background-image: url('./images/bg6.png');
}
.three:hover {
    background-image: url('./images/bg7.png');
}
.four:hover {
    background-image: url('./images/bg8.png');
}
```


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./五彩导航.css">
</head>
<body>
    <div>
        <a href="#" class="one">五彩导航</a>
        <a href="#" class="two">五彩导航</a>
        <a href="#" class="three">五彩导航</a>
        <a href="#" class="four">五彩导航</a>
    </div>
</body>
</html>
```


### 案例三: 小米侧边导航

> 效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051555955.png)
> 总结

1. 这里面的text-indent可以说是超过了我的想象
2. 当链接转化为块级元素后点击区域就可以跳转了

```css
.box {
    width: 234px;
    height: 420px;
    background-color: #2c505f;
}

a {
    display: block;
    width: 234px;
    height: 42px;
    color: white;
    line-height: 42px;
    text-decoration: none;
    font-size: 14px;
    text-indent: 30px;
}
a:hover {
    background-color: red;
}
```


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./小米.css">
</head>
<body>
    <div class="box">
        <a href="#">手机 电话卡</a>
        <a href="#">电视 盒子</a>
        <a href="#">笔记本 显示器</a>
        <a href="#">家电 插线板</a>
        <a href="#">出行 穿戴</a>
        <a href="#">智能 路由器</a>
        <a href="#">电源 配件</a>
        <a href="#">健康 儿童</a>
        <a href="#">耳机 音箱</a>
        <a href="#">生活 箱包</a>
    </div>
</body>
</html>
```


### 案例四: 小米快捷导航

> 效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301051609959.png)

```css
.box {
    height: 40px;
    background-color: #333;
}
.xiaohezi {
    width: 1226px;
    height: 40px;
    font-size: 12px;
    margin: 0 auto;
    color: #b0b0b0;
}
a {
    color: #b0b0b0;
    font-size: 12px;
    text-decoration: none;
    line-height: 40px;
}

a:hover {
    color: white;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./小米快捷导航.css">
</head>
<body>
    <div class="box">
        <div class="xiaohezi">
            <a href="#">小米网</a> | 
            <a href="#">MIUI</a> | 
            <a href="#">米聊</a> | 
            <a href="#">游戏</a> | 
            <a href="#">多看阅读</a> | 
            <a href="#">云服务</a> | 
            <a href="#">小米网移动版</a> | 
            <a href="#">问题反馈</a> | 
            <a href="#">Select Region</a>
        </div>
    </div>
</body>
</html>
```



## 12.0 PxCook的基本使用
给出UI然后制作网页
放大设计图：ctrl++
缩小设计图：ctrl--
移动设计图：空格按着不放，鼠标拖动

> 常用功能

1. 量尺寸，我们可以利用量词工具直接在页面上进行测量，其会自动进行标注
2. 吸颜色

我们除了设计模式之外还有开发模式，可以从psd文件中直接获取数据，包括你选中的元素的各种信息
关键在于布局问题

## 13.0 盒子模型
### 13.1 盒子模型介绍
1.  所有的html元素可以看作是一个盒子，css盒子模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容
2.  盒模型允许我们在其他元素和周围元素边框之间的空间放置元素
CSS 中规定每个盒子分别由：内容区域（content）、内边距区域（padding）、边框区域（border）、外边距区域（margin）构成，这就是 盒子模型

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202212281241950.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202212281241138.png)

### 13.2 内容的宽度和高度
我们之前常用的width和height的高度就是内容的宽度和高度

### 13.3 border相关属性的介绍
> 作用

给设置边框粗细、边框样式、边框颜色效果

单个属性：
边框粗细|border-width|数字+px
边框样式|border-style|实线solid,虚线dashed,点线dotted
边框颜色|border-color|颜色取值

> 连写border

属性值
单个取值的连写，**取值之间以空格隔开，用逗号隔开会没有结果的**
border : 10px solid red;

**注意点**
推荐连写,因为border比较特殊在其必须要同时设置两个属性,style属性是必须设置的,其他属性也要顺便设置,这种同时设置多个的,我们可以连写

通过border-style来调整边框的颜色

边框宽度
```css
border-width来设置宽度 可以指定宽度值,也可以用形容词,thick,medium,thin
p.one
{
    border-style:solid;
    border-width:5px;
}
p.two
{
    border-style:solid;
    border-width:medium;
}
```
边框 颜色
```css
利用border-color来设计边框的颜色 
border-corlor后面跟一个颜色那么就是四个边框的颜色
如果border-corlor后面跟两个颜色就是上下是一个,左右是一个
如果border-color后面跟了三个颜色就是上,下,左右各一个色
如果border-color后面跟了四个颜色,那么就是上,下,左,右各一个颜色
border-style:dotted solid double dashed;
上边框是 dotted
右边框是 solid
底边框是 double
左边框是 dashed

border-style:dotted solid double;
上边框是 dotted
左、右边框是 solid
底边框是 double

border-style:dotted solid;
上、底边框是 dotted
右、左边框是 solid
border-style:dotted;
四面边框是 dotted
```
边框样式
```css
<style>   border-bottom-style这个是定义下边框样式的
p {border-style:solid;}  //定义一个边框格式是实线
p.none {border-bottom-style:none;}  //无边框
p.dotted {border-bottom-style:dotted;}  //圆点边框
p.dashed {border-bottom-style:dashed;}  //虚线边框
p.solid {border-bottom-style:solid;}   //实线边框
p.double {border-bottom-style:double;}  //双实线边框
p.groove {border-bottom-style:groove;}  //凹槽底边框
p.ridge {border-bottom-style:ridge;}    //垄状底边框
p.inset {border-bottom-style:inset;}    //嵌入底边框
p.outset {border-bottom-style:outset;}  //外凸底边框
</style>
```


### 13.4 盒子实际大小的初级计算公式
比如说我们要设置一个400px 400px的盒子并要求其有10px的边框的话
我们直接设置

	div{
	width: 400px;
	height: 400px;
	border: 10px,solid,black
	}

此时盒子的实际大小会是420* 420 并不是我们想设置的,因为此时的border把盒子给撑开了,width和height并不是盒子的宽和高,而是盒子的内容的宽和高,所以这个时候我们要进行手动内减,计算出多余的大小,然后手动减除就好了

盒子宽度 = 左边框 + 内容宽度 + 右边框 
盒子高度 = 上边框 + 内容高度 + 下边框

### 13.5 padding取值介绍

> 作用

设置 边框 与 内容区域 之间的距离

> 属性值padding

> 记忆规则,从上开始复制,然后顺时针赋值,如果哪一边没有赋值的话,看对面的

> 单方向赋值

只给盒子的某个方向单独设置内边距
属性名: padding+方位名词
属性值: 数字+px





### 13.6 自动内减
操作：给盒子设置属性box-sizing:border-box;即可
优点：浏览器会自动计算多余大小，自动在内容中减去

原理是设置完box-sizing:border-box;之后,系统会认为width和height就是盒子的大小,然后系统会根据撑开的大小对盒子进行自动内减

### 13.7 margin属性

> 作用

设置边框以外，盒子与盒子之间的距离,作用是两个元素之间的距离

> 属性名 margin

> 记忆规则

从上开始赋值，然后顺时针赋值，如果没有赋值的，看对面的！！ 和padding的规则一模一样

> margin的单方向设置

属性名: margin - 方位名词
属性值: 数字+px

|方向|属性|效果|
|------|------|------|
|水平方向|margin-left|让当前盒子往右移动|
|水平方向|margin-right|让右边盒子往右移动|
|垂直方向|margin-top|让当前盒子往下移动|
|垂直方向|margin-bottom|让下面盒子往下移动|

往不同方向移动,是反方向的移动

### 13.8 清除默认内外边距
**场景**：浏览器会默认给部分标签设置默认的margin和padding，但一般在项目开始前需要先清除这些标签默认的
margin和padding，后续自己设置

比如：body标签默认有margin：8px
比如：p标签默认有上下的margin
比如：ul标签默认由上下的margin和padding-left

> 解决办法

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061111992.png)
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061111477.png)

这两种代码各有各的好,淘宝的代码虽然写的多,但是对浏览器的性能优化更好,不占用浏览器更多的性能,京东对浏览器的性能要求更高

### 13.9 外边距的正常情况
> 水平方向,会叠加

水平布局 的盒子，左右的margin正常，互不影响
最终两者之间的距离为左右margin的和

### 13.10 外边距的折叠现象

> 垂直方向会出现合并的现象,不会叠加

垂直布局 的 块级元素，上下的margin会合并
最终的结果为两者的margin的最大值

解决办法: 避免就好,只给其中一个盒子设置margin就好

### 13.11 外边距的塌陷
> 场景
> 互相嵌套 的 块级元素，子元素的 margin-top 会作用在父元素上

> 结果导致父元素一起往下移动

> 解决办法
1. 给父元素设置border-top 或者 padding-top（分隔父子元素的margin-top）,添加文本内容也行,其他内容也行,**缺点是这种会改变大盒子的结构**
2. 给父元素设置overflow：hidden;这是一个属性,直接添加就好了
3. 转换成行内块元素
4. 设置浮动

### 13.12 行内元素的margin和padding无效情况

给行内元素设置margin和padding时
1. 水平方向的margin和padding布局中有效！
2. 垂直方向的margin和padding布局中无效！
个人感觉是行内元素本身是没有高度的,高度是由内容撑起来的,所以不能设置margin和padding的垂直方向

### 13.13 不会撑大盒子的特殊情况
块级元素
有一个大盒子,有一个小盒子
不会撑大盒子的特殊情况
1. 如果子盒子没有设置宽度,此时宽度默认是父盒子的宽度
2. 此时给子盒子设置左右的padding或者左右的border此时不会撑大盒子,因为此时最大也就是父盒子的宽度大小,无法在撑大了,浏览器会自动进行内减

## 小案例

###  新浪导航条案例
> 效果图

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301052157806.png)

**对于自己需要高度定义的布局,我们要注意系统默认的影响**
**将a标签转化为行内块元素后,代码格式化后,不同的a标签之间会用换行隔开,换行后会出现空格,这个布局的时候要注意**

**当新浪导航中的链接的字数增加的时候,固定的大小放不下,就会布局混乱,对于这种情况我们由两种解决办法**
1.我们可以**不设置盒子的宽度**,让其由内容撑开,然后此时文字会密集的放在一起,然后就不好看,设置个padding就好，**但是设置了padding之后盒子的大小就会变化，你的布局就会变化，所以注意我们修改padding的时候只需要修改其水平方向的就好，垂直放下的盒子大小不要修改**。
2. 将盒子的宽度增加

```css
/* 清除掉系统默认的margin值 */
* {
    margin: 0;
    padding: 0;
}
.box a {
    display: inline-block;
    font-size: 12px;
    color: #4c4c4c;
    text-decoration: none;
    width: 80px;
    height: 40px;
    text-align: center;
    line-height: 40px;
}
.box {
    height: 40px;
    border-top: 3px solid #ff8500;
    border-bottom: 1px solid #edeef0;
}
.box a:hover {
    background-color: #edeef0;
    color: #ff8400;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./导航条.css">
</head>
<body>
    <div class="box">
        <a href="#">新浪导航</a>
        <a href="#">新浪导航</a>
        <a href="#">新浪导航</a>
        <a href="#">新浪导航</a>
    </div>
</body>
</html>
```

###  网页新闻列表

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301092055433.png)

**对于这个新闻列表padding的设置时,不难看出内容与边框是有间距的,但是对于下边的边距的话,我们要做到随着内容的增加它的边距随着改变,所以其边距我们应该不设置,让其随着内容而改变,故我们设置padding的下边框为0**

**对于这个标题来说,其中我们测量其边距的时候,其只能测出下padding和文字本身大小的盒子,上padding是得不出结果,但是由于浏览器会给文本默认添加行高,导致我们设置的h2盒子的文字并不是紧靠上边界的,对于这种情况,我们要清除行高带来的影响设置==line-height: 1;==,这样的话行高就等于本身,不会在居中了**

```css
* {
    margin: 0px;
    padding: 0px;
}
body {
    line-height: 1;
}
.box {
    width: 500px;
    height: 400px;
    box-sizing: border-box;
    /* 下面的padding设置死了反而不好 */
    padding: 41px 30px 0; 
    border: 1px solid #ccc;
    background-color: #eee;
}
h2 {
    height: 41px;
    border-bottom: 1px solid #ccc;
    box-sizing: border-box;
    font-size: 30px;
}
.box ul {
    list-style: none;
}
.box ul li {
    height: 50px;
    padding-left: 30px;
    border-bottom: 1px dashed #ccc;
    line-height: 50px;
}
.box li a {
    text-decoration: none;
    font-size: 18px;
    color: #666;
}

```


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./news.css">
</head>
<body>
    <div class="box">
        <h2>最新文章/Nex Articles</h2>
        <ul>
            <li><a href="#">北京招聘网页设计，平面设计，php</a></li>
            <li><a href="#">体验javascript的魅力</a></li>
            <li><a href="#">jquery世界来临</a></li>
            <li><a href="#">网页设计师的梦想</a></li>
            <li><a href="#">jquery中的链式编程是什么</a></li>
        </ul>
    </div>
</body>
</html>
```

### 卡片模块案例

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301092145819.png)

**当遇到图片的大小与设置的盒子的大小不同的时候我们可以**
>/* width 100%让其完美填充 */
.box img {
    width: 100%;
}

**盒子的水平居中 auto表示居中**
>margin: 100px auto;
	

```css
* {
    margin: 0;
    padding: 0px;
}
body {
    background-color: #f4f5f9;
}
.box {
    width: 228px;
    height: 270px;
    /* auto是居中的 */
    margin: 100px auto;
    background-color: #fff;
}
/* width 100%让其完美填充 */
.box img {
    width: 100%;
}
.wenzi {
    height: 52px;
    color: #000000;
    font-size: 14px;
    margin: 25px 0px 0px;
    padding: 0px 20px 0px 24px;
}
.explain {
    font-size: 12px;
    color: #929292;

}
.grade {
    color: #f77321;
    margin-left: 24px;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="./卡片.css">
</head>
<body>
    <div class="box">
        <img src="./images/product.png" alt="">
        <div class="wenzi">Android网络图片加载框架详解</div>
        <div class="explain">
            <span class="grade">高级</span>
            • 1125人在学习
        </div>
    </div>
</body>
</html>
```



## 14.0 css标准流
标准流：又称文档流，是浏览器在渲染显示网页内容时默认采用的一套排版规则，规定了应该以何种方式排列元素

常见标准流排版规则： 
1. 块级元素：从上往下，垂直布局，独占一行 
2. 行内元素 或 行内块元素：从左往右，水平布局，空间不够自动换行

## 15.0 浮动
### 15.1 浮动的作用
> 早期的作用

图文环绕
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061743283.png)

> 现在的作用

网页布局
让垂直布局的盒子变成水平布局,一个在左,一个在右

### 15.2 浮动的代码
属性名: float
属性值:
left 左浮动
right 右浮动

### 15.3 浮动的特点
**1. 浮动元素会脱离标准流（简称：脱标），在标准流中不占位置   相当于从地面飘到了空中 ,浮于内容上方,不被内容所限制,可以处于任意的位置**
**当元素飘起来之后,剩余的元素会自动补位**
**例如**
刚开始的图像
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061748758.png)
设置中间的元素右浮动后
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061748449.png)


可以看到下面的元素,会自动上浮,自动补位,因为那个地方的元素飘起来了,已经不占位了

**2. 浮动元素比标准流高半个级别，可以覆盖标准流中的元素** 
例如当设置中间的元素左浮动后
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061750076.png)
中间的元素飘起来,下面的元素补上去,却被上一个元素所覆盖

**3. 浮动找浮动，下一个浮动元素会在上一个浮动元素后面左右浮动** 
当元素都浮动时,就说明它们级别是一样的,所以它们的就会一个挨着一个的按照顺序进行浮动

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061753074.png)


**4. 浮动元素会受到上面元素边界的影响**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301061748449.png)

例如这个蓝色的盒子本来浮动的时候应该是浮动到最上面,但是由于上面的红色盒子有一个边界,所以浮动失败

**5. 浮动元素有特殊的显示效果 一行可以显示多个  可以设置宽高**
因为浮动的元素已经脱离了标准流了,所以不在符合标准流的特征了,对于原本的行内元素例如span等,也可以设置宽和高了,

> 注意点

浮动的元素不能通过text-align:center或者margin:0 auto，让浮动元素本身水平居中

浮动本身就是为了让元素浮动到页面的左边和右边,此时你在让它居中就和出发点矛盾了.

### 15.4 清除浮动
> 含义:清除浮动带来的影响

影响：如果子元素浮动了，此时子元素不能撑开标准流的块级父元素
比如说ul和li这两个,如果li标签设置了浮动的效果,那么即使设置了li的高度,还是撑不开ul,页面中显示的ul的高度还是显示为0,

> 原因
> 子元素浮动后脱标 → 不占位置

>目的： 
需要父元素有高度，从而不影响其他网页元素的布局

### 15.5 直接清除浮动
由于是父元素没有高度,没有被浮动的子元素撑开,我们可以直接设置父元素的高度,
**优点**
简单粗暴，方便
**缺点**
有些布局中不能固定父元素高度。如：新闻列表、京东推荐模块
新闻列表中新闻的条数是不确定的,京东的推荐模块,也不是一开始就很多,你感觉这一面不满意了,下滑会继续扩大这个版面,所以此时父元素就不能固定高度了,要由内容撑开

### 15.6 额外标签法清除浮动
操作：
1. 在父元素内容的最后添加一个块级元素 
2. 给添加的块级元素设置 clear:both

特点：
缺点：会在页面中添加额外的标签，会让页面的HTML结构变得复杂
因为一个web页面往往并不是由一个盒子组成的，而是由多个盒子组成的，你每一个盒子都添加一个div标签，会让html的结构变得混乱

### 15.7 单伪元素清除浮动
操作：用伪元素替代了额外标签
我们直到div中存在的伪元素是用css表达出效果的，这个伪元素的效果我们可以将其转化为块级元素，这样的话伪元素就替代了我们额外添加的块级元素

>基本写法
>.clearfix : : after{
>		content:''
>		display: block;
>		clear :both;
>}

这种写法就是给所有要清除浮动的标签设置clearfix类属性，然后对其的伪元素转化为块级元素，然后清除浮动


> 补充写法
> .clearfix : :after {
> 		content: '.'
> 		display :block;
> 		clear :both;
> 		height :0;
> 		visibility :hidden; //作用是让网页中看不到这个伪元素
> }

这种写法是考虑到有些浏览器对于content内容不能为零，所以考虑到这一点，我们必须强制content里面添加点内容，然后在进行隐藏
**新版本的css中为了区分伪类选择器和伪元素，设定了伪元素是两个冒号，伪类选择器是一个冒号，但是伪元素部分网页中仍然写的是一个冒号，因为这是之前的标准**

### 15.8 双伪元素清除法
> 操作

	.clearfix::before,
        .clearfix::after {
            content: '';
            display: table;
        }
        .clearfix::after {
            clear: both;
        }


这一串代码，记住直接用即可，它不仅仅可以解决清除浮动的问题，还可以解决margin塌陷的现象，因为塌陷是因为margin的父子没有隔开，你加入before这一个伪类之后隔开父子就可以解决这个沦陷问题了


### 15.9 给父元素设置overflow ：hidden
直接给父元素设置 overflow : hidden
特点是方便，设置就省事了，我们还可以设置一个类，然后统一设置这个hidden属性

### 15.10 BFC的介绍
**块格式化上下文（Block Formatting Context）：BFC**
是Web页面的可视CSS渲染的一部分，是块盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域。
**创建BFC方法：**
1. html标签是BFC盒子，**是那个大的html标签**
2. 浮动元素是BFC盒子
3. 行内块元素是BFC盒子
4. overflow属性取值不为visible。如：auto、hidden…，是只要不是vidible的取值，就为BFC的属性
5. ……

**BFC盒子常见特点：**
1. BFC盒子会默认包裹住内部子元素（标准流、浮动）→ 应用：清除浮动，我们可以通过对将父元素转化为BFC盒子，就可与清除父元素和子元素的浮动了，**原因是，子元素撑不开父元素，只要父元素将子元素包裹住，这样子元素变大的时候，父元素就会有高度了**
2. BFC盒子本身与子元素之间不存在margin的塌陷现象 → 应用：解决margin的塌陷
3. ……

## 小案例
### 网页布局案例
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301092207056.png)
**如何让盒子在中间浮动**
因为盒子是无法设置位置的,所以常规方法是无法进行中间浮动的,我们可以设置一个标准流的盒子,然后设置位置,让浮动的元素相对于标准流的盒子进行浮动这样就可以解决这个问题


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .grey {
            width: auto;
            height: 40px;
            background-color: #333333;
        }
        .pink {
            margin: 0 auto;
            width: 1226px;
            height: 100px;
            background-color: pink;
        }
        .smallbox {
            margin: 0 auto;
            width: 1226px;
            height: 460px;
            background-color: #eee;
        }
        .orange {
            background-color: orange;
            width: 234px;
            height: 460px;
            float: left;
        }
        .skyblue {
            width: 992px;
            height: 460px;
            float: left;
            background-color: skyblue;
        }
        
    </style>
</head>
<body>
    <div class="grey"></div>
    <div class="pink"></div>
    <div class="smallbox">
        <div class="orange"></div>
        <div class="skyblue"></div>
    </div>
    
</body>
</html>
```


### 小米商城布局案例

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301092231562.png)

**对于这个案例来说,我们要注意的有以下几点,就是蓝色的盒子是不一样的,上面的和下面的不一样,最右边的两个也和其他不一样**

>.skyblue:nth-child(4n) {
            margin-right: 0;
        }
	.skyblue:nth-child(n+5) {
		margin-bottom: 0;
	}


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .box {
            width: 1226px;
            height: 614px;
            /* background-color: #eee; */
            margin: 100px auto;
        }
        .zise {
            width: 234px;
            height: 614px;
            background-color: #800080;
            float: left;
        }
        .smallbox {
            float: right;
            height: 614px;
            width: 978px;
            /* background-color: pink; */
        }
        .skyblue {
            width: 234px;
            height: 300px;
            background-color: #87ceeb;
            margin: 0 14px 14px 0;
            float: left;
        }
        .skyblue:nth-child(4n) {
            margin-right: 0;
        }
        .skyblue:nth-child(n+5) {
            margin-bottom: 0;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="zise"></div>
        <div class="smallbox">
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
            <div class="skyblue"></div>
        </div>
    </div>

</body>
</html>
```


## 16.0 定位
### 16.1 网页常见布局方式
**标准流**
1. 块级元素独占一行 → 垂直布局
2. 行内元素/行内块元素一行显示多个 → 水平布局
3. 
**浮动**
1. 可以让原本垂直布局的 块级元素变成水平布局

**定位**
1. 可以让元素自由的摆放在网页的任意位置
2. 一般用于 盒子之间的层叠情况

### 16.2 定位的常见应用场景

**可以解决盒子与盒子之间的层叠问题**
定位之后的元素层级最高，可以层叠在其他盒子上面

**可以让盒子始终固定在屏幕中的某个位置**
比如说，对于一些网页，最上面的那一行导航的位置是固定的，即使你滑动滚动条，最上面那一行也是不动的


### 16.3 定位初体验
**需求：页面中两个盒子，要求完成图片的效果，可以如何完成？**
针对于盒子与盒子之间的层叠问题，推荐使用定位完成！
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081125118.png)
**定位步骤**

			/* 1. 设置定位方式 */
            position: absolute;
            /* 2. 设置偏移值 */
            top: 100px;
            left: 100px;


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 200px;
            height: 200px;
        }
        .red {
            background-color: red;
        }
        .blue {
            background-color: blue;
            /* 1. 设置定位方式 */
            position: absolute;
            /* 2. 设置偏移值 */
            top: 100px;
            left: 100px;
        }
    </style>
</head>
<body>
    <div class="red"></div>
    <div class="blue"></div>
</body>
</html>
```


### 16.4 使用定位的步骤
**设置定位方式**
属性名： position
常见属性值
|定位方式|属性值|
|------|------|
|静态定位|static|
|相对定位|relative|
|绝对定位|absolute|
|固定定位|fixed|



**设置偏移值**
偏移值设置分为两个方向，水平和垂直方向各选一个使用即可
选取的原则一般是就近原则 （离哪边近用哪个）

|方向|属性名|属性值|含义|
|------|------|------|------|
|水平|left|数字+px|距离左边的距离|
|水平|right|数字+px|距离右边的距离|
|垂直|top|数字+px|距离上边的距离|
|垂直|bottom|数字+px|距离下边的距离|


### 16.5 静态定位
静态定位就是默认值，就是之前认识的标准流，这个不是重点，默认的都不是重点
**代码position: static;**
**注意点**
1. 静态定位就是之前标准流，不能通过方位属性进行移动，可以试一下
2. 之后说的定位不包括静态定位，一般特指后几种：相对、绝对、固定
**static定位**
```css
div.static {
    position: static;
    border: 3px solid #73AD21;
}
使用static定位的没有特殊的定位,遵循文档的默认定位
```



### 16.6 相对定位
> 介绍

自恋型定位，相对于自己之前的位置进行移动

>代码
>position:relative;

> 特点
1. 需要配合方位属性实现移动
2. 相对于自己原来位置进行移动
3. 在页面中占位置 → 没有脱标

>  应用场景
1. 配合绝对定位组CP（子绝父相）
2. 用于小范围的移动


**relative定位**
```css
h2.pos_left
{
    position:relative;
    left:-20px;
}
h2.pos_right
{
    position:relative;
    left:20px;
}
移动相对定位元素，但它原本所占的空间不会改变。,上面的第一个就是相对于左面移动了20个像素,第二个就是相对于右边移动了20个像素
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 200px;
            height: 200px;
        }
        .red {
            background-color: red;
        }
        .blue {
            background-color: blue;
            /* 1. 设置定位方式 */
            /* position: absolute; */
            /* position: static; */
            position: relative;
            /* 2. 设置偏移值 */
            top: 100px;
            left: 100px;
        }
        .green {
            background-color: green;
        }
    </style>
</head>
<body>
    <div class="red"></div>
    <div class="green"></div>
    <div class="blue"></div>
</body>
</html>
```


### 16.7 绝对定位

> 介绍
> 拼爹型定位，相对于非静态定位的父元素进行定位移动

> 代码:position:absolute;

> 特点
1. 需要配合方位属性实现移动
2. 默认相对于浏览器可视区域进行移动,**是相对于浏览器的**
3. 在页面中不占位置 → 已经脱标

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301090957503.png)
**已经脱标了，不在标准流中了**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        div {
            width: 200px;
            height: 200px;
        }
        .red {
            background-color: red;
        }
        .blue {
            background-color: blue;
            width: 300px;
            height: 300px;
        }
        .green {
            background-color: green;
            position: absolute;
        }
    </style>
</head>
<body>
    <div class="red"></div>
    <div class="green"></div>
    <div class="blue"></div>
</body>
</html>
```


> 应用场景
1. 配合绝对定位组CP（子绝父相）

> 绝对定位相对谁进行偏移
1. 祖先元素中没有定位 → 默认相对于浏览器进行移动

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .father {
            width: 600px;
            height: 600px;
            background-color: pink;
        }
        .son {
            width: 400px;
            height: 400px;
            background-color: skyblue;
        }
        .sun {
            position: absolute;
            right: 0;
            bottom: 0;

            
            width: 200px;
            height: 200px;
            background-color: blue;
        }
    </style>
</head>
<body>
    <div class="father">
        <div class="son">
            <div class="sun"></div>
        </div>
    </div>
</body>
</html>
```

3. 祖先元素中有定位 → 相对于 最近的 有定位 的祖先元素进行移动---**即父元素有定位,爷元素有定位,相对于最近的父元素进行定位,如果祖先元素中没有定位,那么就是相对于浏览器进行移动**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .father {
            position: relative;
            width: 600px;
            height: 600px;
            background-color: pink;
        }
        .son {
            position: relative;
            width: 400px;
            height: 400px;
            background-color: skyblue;
        }
        .sun {
            position: absolute;
            right: 0;
            bottom: 0;


            width: 200px;
            height: 200px;
            background-color: blue;
        }
    </style>
</head>
<body>
    <div class="father">
        <div class="son">
            <div class="sun"></div>
        </div>
    </div>
</body>
</html>
```


### 16.8 固定定位
>介绍：死心眼型定位，相对于浏览器进行定位移动

>代码： position:fixed;

>特点：
1. 需要配合方位属性实现移动,**单独写是没有用的**
2. 相对于浏览器可视区域进行移动,**与父元素无关的**
3. 在页面中不占位置 → 已经脱标,**会覆盖内容,因为没有办法让它返回正常,所以,我们就要修改其他元素的位置,不让其他元素和他进行重叠**


>应用场景：
1. 让盒子固定在屏幕中的某个位置

**fixed定位**
```css
p.pos_fixed
{
    position:fixed;
    top:30px;
    right:5px;
}
元素的位置相对于浏览器窗口是固定位置。
即使窗口是滚动的它也不会移动：
```






**stciky**
```css
div.sticky {
    position: -webkit-sticky; /* Safari */
    position: sticky;
    top: 0;
    background-color: green;
    border: 2px solid #4CAF50;
}
基于用户的滚动而定位,在窗口滚动的时候,当这个文本为到达top:0的时候可以滚动,当达到top:0的时候就粘贴到上面就不动了
```


### 16.9 子绝父相

>场景：让子元素相对于父元素进行自由移动

>含义：
1. 子元素：绝对定位
2. 父元素：相对定位

>子绝父相好处：
1. 父元素是相对定位，则对网页布局影响最小
2. 其实父元素是绝对定位,也可以做到子元素相对于父元素进行移动,但是此时的父元素是脱标的,此时对于其他元素的布局会出现问题

### 16.10 子绝父绝的特殊场景

在使用子绝父相的时候，发现父元素已经有绝对定位了，此时直接子绝即可！**因为父元素可能也是子元素,父元素在满足子绝父相之后是相对的**
原因：
父元素已经有定位已经满足要求，如果盲目修改父元素定位方式，可能会影响之前写好的布局

### 16.11 子绝父相水平居中案例

**代码分析**
```css
.father {
            position: relative;
            width: 600px;
            height: 600px;
            background-color: pink;
        }
        .son {
            position: absolute;
            /* 第一种方法 */
            /* 直接计算居中 */
            /* left: 200px; */

			/* 1. 先让子元素右移动父元素的一半 */
            /* 2. 再左移动子元素的一半 */
            
            left: 50%;  /* 右移父元素的一半,这种百分比一半是相对于父元素而说的 */
            
            /* 1. 子元素的宽度不变,直接计算 */
            /* margin-left: -100px; */
        
            /* 2. 子元素的宽度变化 */
            /* margin-left: 50%;这个是移动大盒子的一半,这种百分比一半是相对于父元素而说的 */
            /* 正确做法 */
            transform: translateX(-50%);
            
            width: 200px;
            height: 100px;
            background-color: skyblue;
        }
```

### 16.12 子绝父相的垂直居中案例


```css
.father {
            position: relative;
            width: 600px;
            height: 600px;
            background-color: pink;
        }
        .son {
            position: absolute;
            left: 50%;
	        transform: translateX(-50%);
	                    
            top: 50%;
            transform: translateY(-50%);

			/* 水平方向又不居中了,这样写完之后translateX(-50%);被覆盖了 */
            /* 因为设置了两个trasform属性,这样下面的那个就会把上面的覆盖了 */
		    /* 正确方法 */
		    
            transform: translate(-50%,-50%);
            width: 200px;
            height: 100px;
            background-color: skyblue;
        }
```


### 16.13 定位的总结

|定位方式|属性值|相对于谁移动|是否占位置|
|------|------|------|------|
|静态定位|static|不能通过方位属性移动|占位置|
|相对定位|relative|相对于自己原来的位置|占位置|
|绝对定位|absolute|相对于最近的且有定位的祖先元素移动|不占位置（脱标）|
|固定定位|fixed|相对于浏览器可视区域|不占位置（脱标）|

### 16.14 元素的层级关系
>不同布局方式元素的层级关系：
- 标准流 < 浮动 < 定位
定位的元素会直接把浮动压在下面

>不同定位之间的层级关系：
1. 相对、绝对、固定默认层级相同
2. 此时HTML中写在下面的元素层级更高，会覆盖上面的元素

### 16.15 更改定位元素的层级

> 场景: 改变定位元素的层级

> 属性名 z-index

> 属性值: 数字
- 数字越大,层级越高
- 为了表示最高,我们可以设置999,比他大也可以,但是没意义了,理解什么意思就好了

**重叠的元素**
```css
img
{
    position:absolute;
    left:0px;
    top:0px;
    z-index:-1;
}
元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素
z-index属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）
一个元素可以有正数或负数的堆叠顺序：
```

## 17.0 装饰

### 17.1 认识基线
**基线：浏览器文字类型元素排版中存在用于对齐的基线（baseline）**
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081207989.png)


### 17.2 文字对齐问题
>场景：解决行内/行内块元素垂直对齐问题

**对于块元素是无效的,是解决行内元素和行内块元素,块元素无效**

>问题：当图片和文字在一行中显示时，其实底部不是对齐的

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081208765.png)

```css
img {
            /* 1. 浏览器的默认值 */
            vertical-align: baseline;
            /* 2. 图片的顶部和文字对齐 */
            vertical-align: top;
            /* 3.图片的底部和文字对齐 */
            vertical-align: bottom;
            /* 4. 中部对齐 */
            vertical-align: middle;
        }
```


### 17.3 垂直对齐方式
> 属性名: vertical-align

|属性值|效果|
|------|------|
|baseline|默认，基线对齐|
|top|顶部对齐|
|middle|中部对齐|
|bottom|底部对齐|

**项目中vertical-align 可以解决的问题**
1. 文本框和表单按钮无法对齐问题
2. input和img无法对齐问题
3. div中的文本框，文本框无法贴顶问题
4. div不设高度由img标签撑开，此时img标签下面会存在额外间隙问题
5. 使用line-height让img标签垂直居中问题

**注意点：**
1. 学习浮动之后，不推荐使用行内块元素让div一行中显
2. 推荐优先使用浮动完成效果

### 17.4 光标类型
> 场景: 设置鼠标光标在元素上时显示的样式

> 属性名: cursor

> 常见属性值

|属性值|效果|
|------|------|
|default|默认值，通常是箭头|
|pointer|小手效果，提示用户可以点击|
|text|工字型，提示用户可以选择文字|
|move|十字光标，提示用户可以移动|

**鼠标光标**
```css
<span style="cursor:auto">auto</span><br>
<span style="cursor:crosshair">crosshair</span><br>
<span style="cursor:default">default</span><br>
<span style="cursor:e-resize">e-resize</span><br>
<span style="cursor:help">help</span><br>
<span style="cursor:move">move</span><br>
<span style="cursor:n-resize">n-resize</span><br>
<span style="cursor:ne-resize">ne-resize</span><br>
<span style="cursor:nw-resize">nw-resize</span><br>
<span style="cursor:pointer">pointer</span><br>
<span style="cursor:progress">progress</span><br>
<span style="cursor:s-resize">s-resize</span><br>
<span style="cursor:se-resize">se-resize</span><br>
<span style="cursor:sw-resize">sw-resize</span><br>
<span style="cursor:text">text</span><br>
<span style="cursor:w-resize">w-resize</span><br>
<span style="cursor:wait">wait</span><br>
我们利用这个cursor:加上后面的元素可以改变鼠标放在这些文本上的时候的形状
```

### 17.5 边框圆角
>场景：
>让盒子四个角变得圆润，增加页面细节，提升用户体验

>属性名：border-radius

>常见取值：数字+px 、百分比

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081215875.png)
==注意点==
**赋值规则：从左上角开始赋值，然后顺时针赋值，没有赋值的看对角！,和那个padding和margin类似**

### 17.6 边框圆角的常见应用
画一个正圆：
1. 盒子必须是正方形
2. 设置边框圆角为盒子宽高的一半 → border-radius:50%
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081216765.png)



胶囊按钮：
1. 盒子要求是长方形
2. 设置 → border-radius：盒子高度的一半

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301081216871.png)


### 17.7 overflow溢出部分显示效果
>溢出部分：
>指的是盒子 内容部分 所超出盒子范围的区域

>场景：
>控制内容溢出部分的显示效果，如：显示、隐藏、滚动条……

> 属性名：overflow

> 常见属性值

|属性值|效果|
|------|------|
|visible|默认值，溢出部分可见|
|hidden|溢出部分隐藏|
|scroll|无论是否溢出，都显示滚动条|
|auto|根据是否溢出，自动显示或隐藏滚动条|

**溢出的元素**
```css
div.ex4 {
    background-color: lightblue;
    width: 110px;
    height: 110px;
    overflow: visible;
}
加入最后overflow: visible;的这个可以达到右图效果
这个处理溢出的效果的话我们可以用visible,hidden,inherit
visible	默认值。内容不会被修剪，会呈现在元素框之外。
hidden	内容会被修剪，并且其余内容是不可见的。
scroll	内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
auto	     如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。
inherit	规定应该从父元素继承 overflow 属性的值。
OS X Lion ( Mac 系统) 系统上，滚动条默认是隐藏的
```

### 17.8 元素本身的隐藏
> 场景
> 让某元素本身在屏幕中不可见。如：鼠标:hover之后元素隐藏

>常见属性：
1. visibility：hidden
2. display：none

> 区别
1. visibility：hidden 隐藏元素本身，并且在网页中 占位置
2. display：none 隐藏元素本身，**在网页中直接不存在了,不占位置了**



> 注意点
- 开发中经常会通过 display属性完成元素的显示隐藏切换
- display：none；（隐藏）、 display：block；（显示）

### 17.9 css轮廓

设置轮廓的样式
```css
轮廓的设置的样式和边框的一摸一样
<style>
p {border:1px solid red;}             //实线
p.dotted {outline-style:dotted;}   //点线轮廓
p.dashed {outline-style:dashed;}   //虚线轮廓
p.double {outline-style:double;}   //双线轮廓
p.groove {outline-style:groove;}   //凹槽轮廓
p.ridge {outline-style:ridge;}     //垄状轮廓
p.inset {outline-style:inset;}     //嵌入轮廓
p.outset {outline-style:outset;}   //外凸轮廓
</style>
```
 轮廓的颜色和宽度
 ```css
 p 
{
	border:1px solid red;
	outline-style:dotted;
        outline-color:#00ff00;   //设置边框的颜色
}
p.two
{
        border:1px solid red;
        outline-style:dotted;
        outline-width:5px;       //设置边框的宽度,可以指定大小,也可以指定特征
}
```

