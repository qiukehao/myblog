---
{"dg-publish":true,"permalink":"/02java//02java-web/02-html-css/","dgPassFrontmatter":true}
---

## 网页初识
**网页包含哪些部分**
文字, 图片, 音频, 视频, 超链接
**我们看到的网页, 背后的本质是什么?**
程序员写的前端代码
**前端的代码是如何转化为用户眼中的网页**
通过浏览器转化 (解析和渲染)成用户的网页
浏览器对代码进行解析和渲染的部分, 称为浏览器内核

为了防止不同的浏览器内核解析的时候导致页面显示效果不同, 我们需要一个标准, 因此这就诞生了这个 Web 标准
Web 标准也称为网页标准，由一系列的标准组成，大部分由 W 3 C ( world wide web Consortium，万维网联盟）负责制定。
三个组成部分:
1. HTML: 负责网页的结构（页面元素和内容)。
2. CSS: 负责网页的表现（页面元素的外观、位置等页面样式，如: 颜色、大小等)。
3. JavaScript:负责网页的行为 (交互效果)。

## HTML 和 CSS 的基本知识

### CSS 引入
CSS 引入方式：
1. 行内样式：写在标签的 style 属性中（不推荐）这种方式只能修改一个标签的样式
**补充**
这个行内样式使用空格作为多个属性的分隔符的，我刚开始用的是逗号分隔符，发现无法获取对象,，
3. 内嵌样式：写在 style 标签中（可以写在页面任何位置，但通常约定写在 head 标签中）
4. 外联样式：写在一个单独的. Css 文件中（需要通过 link 标签在网页中引入）
颜色表示形式：

| 表示方式    | 表示含义                | 取值                                       |
|---------|---------------------|------------------------------------------|
| 关键字     | 预定义的颜色名             | red、green、blue...                        |
| rgb 表示法  | 红绿蓝三原色，每项取值范围：0-255 |rgb (0,0,0)、rgb (255,255,255)、rgb (255,0,0) |
| 十六进制表示法 |\ #开头 ，将数字转换成十六进制表示|\ #000000 、 \ #ff0000 、 \ #cccccc ，简写： \ #000 \ #ccc |

### CSS 选择器
[[06前端/CSS基础笔记\|CSS基础笔记]]
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061327021.png)

Id 选择器的优先级最高, 其次是这个类选择器, 然后是这个元素选择器
类选择器可以有一个标签都是一个类, 但是这个 id 的话是唯一的, 其实这个优先级顺序就是谁的指定范围越小, 谁的优先级越高

### 标题图片正文
HTML 是超文本标记形语言，我们通过标签来对这个页面进行管理
其中比较常用的有
图片 img 下划线 hr 标题 h1,h 2 h 3 h 4
```html
    <img src="./images/news_logo.png"> 新浪政务 > 正文
    <h1>焦点访谈: 中国底气 新思想夯实大国粮仓</h1>
    <hr>
    <span>2023/10/6 周五 11:00</span>
    <hr>
```
其中对于某些标签呢我们可以设置样式, 比如说这个 img 标签, 我们可以设置这个 img 标签的 width 喝 height, 我们可以指定这个宽度和高度的具体像素, 也可以通过百分比来设置这个图片占据这个父标签的大小, 比如说这个 img 是在这个 body 下的, 那么 width50%就是指这个图片占据父类对象 50%, **但是要注意这个 width 和这个 height 我们要设置的时候最好是只设置一个, 因为设置一个, 另一个是等比例放大的, 但是你如果两个元素都同时设置了, 那么这个就有可能改变图片的纵横比, 就会导致这个图片失去了原有的样式**

### 超链接
target 是指定这个链接的打开方式, \_self 是在当前标签页进行打开.\_blank 是指定这个页面是在新标签页进行打开的.
```html
<span><a href="https://blog.csdn.net/everything_study?spm=1008.2028.3001.5343" target="_blank">新浪政务</a> > 正文</span>
```

超链接默认是有下划线的, 我们可以设置这个 text\_decoration 属性来设置这个下划线的有无.
```css
        a {
            text-decoration: none;
        }
```

### 视频标签

视频标签: \<video\>
- 属性:
	- src: 规定视频的 url
	- Controls: 显示播放控件
	- Width: 播放器的宽度
	- height: 播放器的高度
- 音频标签: \<audio\>
    - 属性:
        - src: 规定音频的url 
        - Controls: 显示播放控件
我们要注意这个音频和视频标签我们一定要设置这个播放空间, 否则的话只能显示这个视频的开始页, 是无法进行播放的, 我们只有显示了这个播放按钮之后才能进行播放视频

### 正文排版
**常用的标签**
- 换行标签: \<br\>
    - 注意: 在HTML页面中,我们在编辑器中通过回车实现的换行, 仅仅在文本编辑器中会看到换行效果, 浏览器是不会解析的, HTML中换行需要通过br标签
- 段落标签:\<p\>
    - 如: \<p> 这是一个段落 \</p>

|效果|标签|标签(强调)|
|---|---|---|
|加粗|b|strong|
|倾斜|i|em|
|下划线|u|ins|
|删除线|s|del|

前面的标签 b、i、u、s 就仅仅是实现加粗、倾斜、下划线、删除线的效果，是没有强调语义的。而后面的 strong、em、ins、del 在实现加粗、倾斜、下划线、删除线的效果的同时，还带有强调语义。
**常用的 css 样式**
- text-indent: 设置段落的首行缩进
- line-height: 设置行高
- Text-align: 设置对齐方式, 可取值为 left / center / right

**特殊符号**

| 显示结果 | 描述   | 占位符  |
| :------- | :----- | :------ |
|          | 空格   | \&nbsp; |
| <        | 小于号 | \&lt;   |
| >        | 大于号 | \&gt;   |
| &        | 和号   | \&amp;  |
| "        | 引号   | \&quot; |
| '        | 撇号   | \&apos; |

### 盒子模型
- 盒子：页面中所有的元素（标签），都可以看做是一个盒子，由盒子将页面中的元素包含在一个矩形区域内，通过盒子的视角更方便的进行页面布局
- 盒子模型组成：内容区域（content）、内边距区域（padding）、边框区域（border）、外边距区域（margin）
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061349451.png)
CSS 盒子模型，其实和日常生活中的包装盒是非常类似的，就比如：
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061350856.png)
盒子的大小，其实就包括三个部分： border、padding、content，而 margin 外边距是不包括在盒子之内的。


###  布局标签

- 布局标签：实际开发网页中，会大量频繁的使用 div 和 span 这两个没有语义的布局标签。
- 标签：\<div>\<span>
- 特点：
    - div标签：
        - 一行只显示一个（独占一行)
        - 宽度默认是父元素的宽度，高度默认由内容撑开
        - 可以设置宽高（width、height）
    - span标签：
        - 一行可以显示多个
        - 宽度和高度默认由内容撑开 
        - 不可以设置宽高（width、height）

### 表格标签
在网页中以表格（行、列）形式整齐展示数据，我们在一些管理类的系统中，会看到数据通常都是以表格的形式呈现出来的，比如：班级表、学生表、课程表、成绩表等等。
- \<table> : 用于定义整个表格, 可以包裹多个 \<tr>，常用属性如下： 
  - border：规定表格边框的宽度
  - width：规定表格的宽度
  - cellspacing: 规定单元之间的空间
- \<tr> : 表格的行，可以包裹多个 \<td>  
- \<td> : 表格单元格 (普通)，可以包裹内容 , 如果是表头单元格，可以替换为 \<th>  
```html
    <table border="1px",width="600px",cellspacing="0">
        <tr>
            <th>name</th>
            <th>sex</th>
            <!-- <th>sf</th> -->
        </tr>
        <tr>
            <td>A</td>
            <td>B</td>
            <td>C</td>
        </tr>
        <tr>
            <td>A</td>
            <td>B</td>
            <td>C</td>
        </tr>
        <tr>
            <td>A</td>
            <td>B</td>
            <td>C</td>
        </tr>
    </table>
```

结果如下
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061358363.png)
当然这个单元格里面 (td 和 th)里面不仅仅能放置这个文字, 还能防止图片, 超链接等
例如
```html
        <tr>
            <td>2</td>
            <td> <img src="img/alibaba.jpg"  width="100px"> </td>
            <td>阿里</td>
            <td>阿里巴巴集团控股有限公司</td>
        </tr>
```

### 表单标签
在一个表单中，可以存在很多的表单项，而虽然表单项的形式各式各样，但是表单项的标签其实就只有三个，分别是：
\<input>: 表单项 , 通过 type 属性控制输入形式。

|type 取值|**描述**|
|---|---|
|text|默认值，定义单行的输入字段|
|password|定义密码字段|
|radio|定义单选按钮|
|checkbox|定义复选框|
|file|定义文件上传按钮|
|date/time/datetime-local|定义日期/时间/日期时间|
|number|定义数字输入框|
|email|定义邮件输入框|
|hidden|定义隐藏域|
|submit / reset / button|定义提交按钮 / 重置按钮 / 可点击按钮|

 \<select>: 定义下拉列表, 
 \<option> 定义列表项
\<textarea>: 文本域

```html
    <form action="">
        姓名 <input type="text"><br>
        密码 <input type="password"><br>
        性别 <input type="radio", name ="gender">男 <input type="radio", name = "gender"> 女<br>
        爱好 <input type="checkbox"> 篮球 <input type="checkbox"> 足球<br>
        图像 <input type="file"><br>
        生日 <input type="date"><br>
        时间 <input type="time"><br>
        日期时间 <input type="datetime-local"><br>
        邮箱 <input type="email"><br>
        年龄 <input type="number"><br>
        学历 <select name="degree"><br>
            <option value="1">本科</option><br>
            <option value="2">大专</option><br>
            <option value="3">研究生</option><br>
        </select><br>
        描述 <textarea cols="30" rows="10"></textarea><br>
        <button type="button">按钮</button>
        <button type="reset">重置</button>
        <button type="submit">提交</button>
    </form>
```
结果
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061415318.png)

> [!warning] 
> 值得注意的是上面的表单代码只是用来进行页面展示的, 如果我们真的想提交表单, 我们要给这个 form 标签的 action 属性设置值, 如果不设置值的话, 就会默认的提交到当前页面, 还有就是这个 input 标签我们要设置这个 name, 如果不设置 name 是无法提交数据的, 根本不知道你提交的是什么东西
> - action: 规定表单提交时，向何处发送表单数据，表单提交的 URL。
> - Method: 规定用于发送表单数据的方式，常见为： GET、POST。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061422823.png)

Post 提交的结果可以在开发者控制台中的 Network和 Payload 中找到
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310061429265.png)
