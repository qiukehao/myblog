---
{"dg-publish":true,"permalink":"/06/webapi/","dgPassFrontmatter":true}
---

> 学习目标：
>
> 能够通过ID来获取元素
> 能够通过标签名来获取元素
> 能够通过class来获取元素
> 能够通过选择器来获取元素
> 能够获取body和html元素
> 能够给元素注册事件
> 能够修改元素的内容
> 能够区分innerText和innerHTML的区别
> 能够修改像div这类普通元素的属性
> 能够修改表单元素的属性
> 能够修改元素的样式属性

# DOM和操作对象
## 1.1. Web API介绍
### 1.1.1 API的概念

API（Application Programming Interface，应用程序编程接口）是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组例程的能力，而又无需访问源码，无需理解其内部工作机制细节，只需直接调用使用即可。

类似于手机充电的接口，我们要实现手机充电则个功能，我们不需要关心手机充电器是怎么制作的，不需要关心手机内部变压器，我们只需要拿着充电线插进充电接口就可以充电，这个充电接口就是一个API



> 举例解释什么是API。
>
> 例如，
>
> ​	C语言中有一个函数 fopen()可以打开硬盘上的文件，这个函数对于我们来说，就是一个C语言提供的打开文件的工具。
>
> ​	javascript中有一个函数alert()可以在页面弹一个提示框，这个函数就是js提供的一个弹框工具。
>
> 这些工具（函数）由编程语言提供，内部的实现已经封装好了，我们只要学会灵活的使用这些工具即可。

### 1.1.2 Web  API的概念

​	Web API 是浏览器提供的一套操作浏览器功能和页面元素的 API ( BOM 和 DOM )。

​	现阶段我们主要针对于浏览器讲解常用的 API , 主要针对浏览器做交互效果。比如我们想要浏览器弹出一个警示框， 直接使用 alert(‘弹出’)，alert就是浏览器的一个接口

​	MDN 详细 API : https://developer.mozilla.org/zh-CN/docs/Web/API

​	因为 Web API 很多，所以我们将这个阶段称为 Web APIs。

​	此处的 Web API 特指浏览器提供的一系列API(很多函数或对象方法)，即操作网页的一系列工具。例如：操作html标签、操作页面地址的方法。

### 1.1.3 API 和 Web  API 总结

1. API 是为我们程序员提供的一个接口，帮助我们实现某种功能，我们会使用就可以了，不必纠结内部如何实现
2. 好多语言都有自己的api
3. Web API 主要是针对于浏览器提供的接口，主要针对于浏览器做交互效果。
4. Web API 一般都有输入和输出（函数的传参和返回值），Web API 很多都是方法（函数）
5. 学习 Web API 可以结合前面学习内置对象方法的思路学习

## 1.2. DOM 介绍

### 1.2.1 什么是DOM

​	文档对象模型（Document Object Model，简称DOM），是 [W3C](https://baike.baidu.com/item/W3C) 组织推荐的处理[可扩展标记语言](https://baike.baidu.com/item/%E5%8F%AF%E6%89%A9%E5%B1%95%E7%BD%AE%E6%A0%87%E8%AF%AD%E8%A8%80)（html或者xhtml）的标准[编程接口](https://baike.baidu.com/item/%E7%BC%96%E7%A8%8B%E6%8E%A5%E5%8F%A3)。

​	W3C 已经定义了一系列的 DOM 接口，通过这些 DOM 接口可以改变网页的内容、结构和样式。

> DOM是W3C组织制定的一套处理 html和xml文档的规范，所有的浏览器都遵循了这套标准。

### 1.2.2. DOM树



DOM树 又称为文档树模型，把文档映射成树形结构，通过节点对象对其处理，处理的结果可以加入到当前的页面。

- 文档：一个页面就是一个文档，DOM中使用document表示
- 元素：页面中所有标签都是元素，DOM中使用element表示
- 节点：网页中的所有内容，在文档树中都是节点（标签、属性、文本、注释等），使用node表示
- 标签节点：网页中的所有标签，通常称为元素节点，又简称为“元素”，使用element表示


## 1.3. 获取元素

为什么要获取页面元素？

例如：我们想要操作页面上的某部分(显示/隐藏，动画)，需要先获取到该部分对应的元素，再对其进行操作。

### 1.3.1. 根据ID获取

```js
语法：document.getElementById(id)
作用：根据ID获取元素对象
参数：id值，区分大小写的字符串
返回值：元素对象 或 null
```

**案例代码**

```js
<body>
    <div id="time">2019-9-9</div>
    <script>
        // 因为我们文档页面从上往下加载，所以先得有标签 所以我们script写到标签的下面
        var timer = document.getElementById('time');
        console.log(timer);
        console.log(typeof timer);
        // console.dir 打印我们返回的元素对象 更好的查看里面的属性和方法
        console.dir(timer);
    </script>
</body>
```

```js
<script>
    //1. 我们文档页面从上往下加载，所以我们要先有标签，把script写到标签的下面
    //2. get获得element元素by通过，驼峰命名法
    //3. 参数id是大小写敏感的字符串
    //4. 内部是有参数的，参数是要获得的元素的id
    var timer = document.getElementById('time');
console.log(timer);
// 返回的类型是对象数据类型
console.log(typeof timer);
// 输出这个对象的所有信息,可以打印我们返回的元素d对象，更好的查看里面的属性和方法
console.dir(timer);
</script>
```

### 1.3.2. 根据标签名获取元素

```
语法：document.getElementsByTagName('标签名') 或者 element.getElementsByTagName('标签名') 
作用：根据标签名获取元素对象
参数：标签名
返回值：元素对象集合（伪数组，数组元素是元素对象）
```

==利用标签名这个获取元素对象我们一个注意点是返回值是对象，我们不能直接用那个变量名作为对象，而是要用数组的表示方法来显示对象==

**案例代码**

```javascript
<body>
    <ul>
        <li>知否知否，应是等你好久11</li>
        <li>知否知否，应是等你好久22</li>
        <li>知否知否，应是等你好久33</li>
        <li>知否知否，应是等你好久44</li>
        <li>知否知否，应是等你好久55</li>
    </ul>
    <ul id="nav">
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
        <li>生僻字</li>
    </ul>
    <script>
        // 1.返回的是 获取过来元素对象的集合 以伪数组的形式存储的
        var lis = document.getElementsByTagName('li');
        console.log(lis);
        console.log(lis[0]);
        // 2. 我们想要依次打印里面的元素对象我们可以采取遍历的方式
        for (var i = 0; i < lis.length; i++) {
            console.log(lis[i]);
        }
        // 3. element.getElementsByTagName()  可以得到这个元素里面的某些标签
        var nav = document.getElementById('nav'); // 这个获得nav 元素
        var navLis = nav.getElementsByTagName('li');
        console.log(navLis);
    </script>
</body>
```

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129803.png)

注意：getElementsByTagName()获取到是动态集合，即：当页面增加了标签，这个集合中也就增加了元素。

**动态的意思就是返回的元素会根据里面内容的修改而修改**

**对于多个标签 ,有重复的情况的话,我们可以先通过标签id获得它的父元素的返回对象,然后在通过tag获得这个标签的返回值,document是选着这个文件的所有标签,如果是个id名,我们可以根据这个id来返回对象**

**如果是获取id我们是getelement,如果是标签我们是getelements**

### 1.3.3. H5新增获取元素方式
![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129822.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129840.png)
**案例代码**
```js
<body>
    <div class="box">盒子1</div>
    <div class="box">盒子2</div>
    <div id="nav">
        <ul>
            <li>首页</li>
            <li>产品</li>
        </ul>
    </div>
    <script>
        // 1. getElementsByClassName 根据类名获得某些元素集合
        var boxs = document.getElementsByClassName('box');
        console.log(boxs);
        // 2. querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav,通过添加符号才能精准定位啊,当然标签就不用加符号了
        var firstBox = document.querySelector('.box');
        console.log(firstBox);
        var nav = document.querySelector('#nav');
        console.log(nav);
        var li = document.querySelector('li');
        console.log(li);
        // 3. querySelectorAll()返回指定选择器的所有元素对象集合
        var allBox = document.querySelectorAll('.box');
        console.log(allBox);
        var lis = document.querySelectorAll('li');
        console.log(lis);
    </script>
</body>
```

### 1.3.4 获取特殊元素（body，html）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129859.png)

**对于这些标签,我们其实 也可以通过添加类名和id名来获取这个对象,但是因为这个标签是太少了,所以 我们可以特殊情况特殊对待**

```js
var bodyEle = document.body;
这个没有括号啊
var htmlEle = document.documentElement;
这个也没有括号
```


## 1.4. 事件基础

### 1.4.1. 事件概述

**对于网页来说,我们的效果是有个触发按钮的,比如说悬停出现菜单的操作,只有鼠标放在上面才会出现效果,这种行为就是事件**

JavaScript 使我们有能力创建动态页面，而事件是可以被 JavaScript 侦测到的行为。

简单理解： **触发--- 响应机制**。

​	网页中的每个元素都可以产生某些可以触发 JavaScript 的事件，例如，我们可以在用户点击某按钮时产生一个 事件，然后去执行某些操作。

### 1.4.2. 事件三要素

**事件有三部分组成**

- 事件源（谁）：触发事件的元素----就是谁被触发了,那怎么获取这个时间呢,那么我们就是取一个id
- 事件类型（什么事件）： 例如 click 点击事件
- 事件处理程序（做啥）：事件触发后要执行的代码(函数形式)，事件处理函数

**第一种鼠标点击触发onclick**

点击弹出对话框

**案例代码**

```js
<body>
    <button id="btn">唐伯虎</button>
    <script>
        // 点击一个按钮，弹出对话框
        // 1. 事件是有三部分组成  事件源  事件类型  事件处理程序   我们也称为事件三要素
        //(1) 事件源 事件被触发的对象   谁  按钮
        var btn = document.getElementById('btn');
        //(2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
        //(3) 事件处理程序  通过一个函数赋值的方式 完成
        btn.onclick = function() {
            alert('点秋香');
        }
    </script>
</body>
```

### 1.4.3. 执行事件的步骤
![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129888.png)

**案例代码**
```js
<body>
    <div>123</div>
    <script>
        // 执行事件步骤
        // 点击div 控制台输出 我被选中了
        // 1. 获取事件源
        var div = document.querySelector('div');
        // 2.绑定事件 注册事件
        // div.onclick 
        // 3.添加事件处理程序 
        div.onclick = function() {
            console.log('我被选中了');
        }
    </script>
</body>
```

### 1.4.4. 常见的鼠标事件
![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129908.png)

### 1.4.5. 分析事件三要素

- 下拉菜单三要素

- 关闭广告三要素

## 1.5. 操作元素

​	JavaScript的 DOM 操作可以改变网页内容、结构和样式，我们可以利用 DOM 操作元素来改变元素里面的内容、属性等。（注意：这些操作都是通过元素对象的属性实现的）

### 1.5.1. 改变元素内容（获取或设置）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129928.png)

**innerText改变元素内容**

```js
<body>
    <button>显示当前系统时间</button>
    <div>某个时间</div>
    <p>1123</p>
    <script>
        // 当我们点击了按钮，  div里面的文字会发生变化
        // 1. 获取元素 
        var btn = document.querySelector('button');
        var div = document.querySelector('div');
        // 2.注册事件
        btn.onclick = function() {
            // div.innerText = '2019-6-6';
            div.innerHTML = getDate();
        }
        function getDate() {
            var date = new Date();
            // 我们写一个 2019年 5月 1日 星期三
            var year = date.getFullYear();
            var month = date.getMonth() + 1;
            var dates = date.getDate();
            var arr = ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'];
            var day = date.getDay();
            return '今天是：' + year + '年' + month + '月' + dates + '日 ' + arr[day];
        }
		// 我们元素不用添加注册事件,当浏览器刷新后直接获取,这个时候我们只需要把操作样式直接去掉就好了
		var p = document.querySelector('p');
        p.innerText = getDate();
    </script>
</body>
```

**innerText和innerHTML的区别**

- 获取内容时的区别：

​	innerText会去除空格和换行，而innerHTML会保留空格和换行	

- 设置内容时的区别：

​	innerText不会识别html标签,例如strong等样式标签这个是识别不出来的，而innerHTML会识别

innertext和innerHTMl不仅可以用来修改标签里面的元素,还可以获取标签里面的元素,但是text获取内容的死后,会去除空格和换行的,HTML会保留空格和换行,标签也保留

**案例代码**

```js
<body>
    <div></div>
    <p>
        我是文字
        <span>123</span>
    </p>
    <script>
        // innerText 和 innerHTML的区别 
        // 1. innerText 不识别html标签 非标准  去除空格和换行
        var div = document.querySelector('div');
        // div.innerText = '<strong>今天是：</strong> 2019';
        // 2. innerHTML 识别html标签 W3C标准 保留空格和换行的
        div.innerHTML = '<strong>今天是：</strong> 2019';
        // 这两个属性是可读写的  可以获取元素里面的内容
        var p = document.querySelector('p');
        console.log(p.innerText);
        console.log(p.innerHTML);
    </script>
</body>
```

### 1.5.2. 常用元素的属性操作
![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129947.png)

**获取属性的值**

> 元素对象.属性名,**这个元素对象就是我们的一个返回值**

**设置属性的值**

> 元素对象.属性名 = 值

**案例代码**

```js
<body>
    <button id="ldh">刘德华</button>
    <button id="zxy">张学友</button> <br>
    <img src="images/ldh.jpg" alt="" title="刘德华">
    <script>
        // 修改元素属性  src
        // 1. 获取元素
        var ldh = document.getElementById('ldh');
        var zxy = document.getElementById('zxy');
        var img = document.querySelector('img');
        // 2. 注册事件  处理程序
        zxy.onclick = function() {
            img.src = 'images/zxy.jpg';
            img.title = '张学友思密达';
        }
        ldh.onclick = function() {
            img.src = 'images/ldh.jpg';
            img.title = '刘德华';
        }
    </script>
</body>
```



### 1.5.3. 案例：分时问候

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129965.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151129986.png)



```js
	<body>
		<img src="./images/s.gif" alt="" />
		<div id="text">亲上午好,好好写代码</div>
		<script>
			var img = document.querySelector('img');
			var text = document.getElementById('text');
			var nowtime = +new Date();
			var time = nowtime / 1000;
			var hour = parseInt((time / 60 / 60) % 24);
			if (hour <= 9 && hour >= 6) {
				img.src = './images/z.gif';
				text.innerText = '亲,早起身体好';
			} else if (hour <= 12) {
				img.src = './images/s.gif';
				text.innerText = '亲,上午起来干活了';
			} else if (hour <= 20) {
				img.src = './images/x.gif';
				text.innerText = '亲,下午记得午睡哦';
			} else {
				img.src = './images/w.gif';
				text.innerText = '亲,晚上早点睡,身体好';
			}
		</script>
	</body>
```





### 1.5.4. 表单元素的属性操作

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130009.png)

**获取属性的值**

> 元素对象.属性名

**设置属性的值**

> 元素对象.属性名 = 值
>
> 表单元素中有一些属性如：disabled、checked、selected，元素对象的这些属性的值是布尔型。这些类型不能通过inner.html和inner.text来进行修改,我们要直接修改他们的属性

**案例代码**

```js
<body>
    <button>按钮</button>
    <input type="text" value="输入内容">
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var input = document.querySelector('input');
        // 2. 注册事件 处理程序
        btn.onclick = function() {
            // 表单里面的值 文字内容是通过 value 来修改的
            input.value = '被点击了';
            // 如果想要某个表单被禁用 不能再点击 disabled  我们想要这个按钮 button禁用
            // btn.disabled = true;
            this.disabled = true;
            // this 指向的是事件函数的调用者 btn,这个更加简单
        }
    </script>
</body>
```

### 1.5.5. 案例：仿京东显示密码

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130032.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130053.png)



```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			.box {
				position: relative;
				width: 400px;
				border-bottom: 1px solid red;
				margin: 100px auto;
			}
			.box input {
				width: 300px;
				height: 30px;
				outline: none;
				border: 0px;
			}
			.box img {
				width: 24px;
				position: absolute;
				top: 5px;
				right: 50px;
			}
			.box span {
				font-size: 12px;
				position: absolute;
				right: 0;
				top: 10px;
			}
		</style>
	</head>
	<body>
		<div class="box">
			<input type="password" id="psd" />
			<label for="">
				<img src="./images/close.png" alt="" id="eye" />
			</label>
			<span>显示密码</span>
		</div>
		<script>
			// 1. 获取元素
			var eye = document.getElementById('eye');
			var psd = document.getElementById('psd');
			// 2. 处理事件
			var flag = 0;
			eye.onclick = function () {
				if (flag == 0) {
					eye.src = './images/open.png';
					psd.type = 'text';
					flag = 1;
				} else {
					eye.src = './images/close.png';
					psd.type = 'password';
					flag = 0;
				}
			};
		</script>
	</body>
</html>

```



### 1.5.6. 样式属性操作

我们可以通过 JS 修改元素的大小、颜色、位置等样式。

**常用方式**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130073.png)



#### 方式1：通过操作style属性

> 元素对象的style属性也是一个对象！
>
> 元素对象.style.样式属性 = 值;

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130095.png)

**案例代码**

```js
<body>
    <div></div>
    <script>
        // 1. 获取元素
        var div = document.querySelector('div');
        // 2. 注册事件 处理程序
        div.onclick = function() {
            // div.style里面的属性 采取驼峰命名法 
            this.style.backgroundColor = 'purple';
            this.style.width = '250px';
        }
    </script>
</body>
```



#### 案例：淘宝点击关闭二维码

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130118.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130139.png)

**用i标签进行调整关闭**

#### 案例：循环精灵图背景

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130157.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130178.png)

**注意坐标的书写方式,中间用空格隔开,实际上是一个字符串**

> lis[i].style.backgroundPosition = '0 -' + index + 'px';

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}

			li {
				list-style-type: none;
			}

			.box {
				width: 250px;
				margin: 100px auto;
			}

			.box li {
				float: left;
				width: 24px;
				height: 24px;
				background-color: pink;
				margin: 15px;
				background: url(./images/sprite.png) no-repeat;
			}
		</style>
	</head>
	<body>
		<div class="box">
			<ul>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
				<li></li>
			</ul>
		</div>
		<script>
			var lis = document.querySelectorAll('li');
			for (var i = 0; i < lis.length; i++) {
				var index = i * 44;
				lis[i].style.backgroundPosition = '0 -' + index + 'px';
			}
		</script>
	</body>
</html>
```







#### 案例：显示隐藏文本框内容

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130201.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130222.png)

> 这种验证鼠标的焦点的操作是需要点击的不是移开就可以进行修改了



#### 方式2：通过操作className属性

> 元素对象.className = 值;
>
> 因为class是关键字，所有使用className。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130242.png)

> **就是一个简单的添加一个类名而已,我们在新添加的这个类名里,设置一个新的样式**

**案例代码**

```js
<body>
    <div class="first">文本</div>
    <script>
        // 1. 使用 element.style 获得修改元素样式  如果样式比较少 或者 功能简单的情况下使用
        var test = document.querySelector('div');
        test.onclick = function() {
            // this.style.backgroundColor = 'purple';
            // this.style.color = '#fff';
            // this.style.fontSize = '25px';
            // this.style.marginTop = '100px';

            // 2. 我们可以通过 修改元素的className更改元素的样式 适合于样式较多或者功能复杂的情况
            // 3. 如果想要保留原先的类名，我们可以这么做 多类名选择器
            // this.className = 'change';
            this.className = 'first change';
            就是添加一个类名
        }
    </script>
</body>
```



> 为了保留类名,我们可以添加两个类名,然后用空格隔开



#### 案例：密码框格式提示错误信息

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130264.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130284.png)

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			div {
				width: 600px;
				margin: 100px auto;
			}

			.message {
				display: inline-block;
				font-size: 12px;
				color: #999;
				background: url(images/mess.png) no-repeat left center;
				padding-left: 20px;
			}

			.wrong {
				color: red;
				background-image: url(images/wrong.png);
			}

			.right {
				color: green;
				background-image: url(images/right.png);
			}
		</style>
	</head>
	<body>
		<div class="register">
			<input type="password" class="ipt" />
			<p class="message">请输入6~16位密码</p>
		</div>
		<script>
			// 首先判断的事件是表单失去焦点 onblur
			// 如果输入正确则提示正确的信息颜色为绿色小图标变化
			// 如果输入不是6到16位，则提示错误信息颜色为红色 小图标变化
			// 因为里面变化样式较多，我们采取className修改样式
			// 1. 获取对象
			var ipt = document.querySelector('.ipt');
			var message = document.querySelector('.message');
			// 2. 执行事件
			ipt.onblur = function () {
				if (this.value.length < 6 || this.value.length > 16) {
					message.innerHTML = '你输入的位数不对';
					message.className = 'message wrong';
				} else {
					message.innerHTML = '你输入的正确';
					message.className = 'message right';
				}
			};
		</script>
	</body>
</html>
```





## 1.6. 今日总结

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151130307.png)





# 排他操作和节点操作

> 学习目标：
>
> 能够说出排他操作的一般实现步骤
>
> 能够使用html5中的dataset方式操作自定义属性
>
> 能够根据提示完成百度换肤的案例
>
> 能够根据提示完成全选案例
>
> 能够根据提示完成tab栏切换案例
>
> 能够区分元素节点、文本节点、属性节点
>
> 能够获取指定元素的父元素
>
> 能够获取指定元素的所有子元素
>
> 能够说出childNodes和children的区别
>
> 能够使用createElement创建页面元素

## 1.1. 排他操作

### 1.1.1 排他思想

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131176.png)

如果有同一组元素，我们想要某一个元素实现某种样式， 需要用到循环的排他思想算法：

1. 所有元素全部清除样式（干掉其他人）

2. 给当前元素设置样式 （留下我自己）

3. 注意顺序不能颠倒，首先干掉其他人，再设置自己

```js
    <button>按钮1</button>
    <button>按钮2</button>
    <button>按钮3</button>
    <button>按钮4</button>
    <button>按钮5</button>
    <script>
        // 1. 获取所有按钮元素
        var btns = document.getElementsByTagName('button');
        // btns得到的是伪数组  里面的每一个元素 btns[i]
        for (var i = 0; i < btns.length; i++) {
            btns[i].onclick = function() {
                // (1) 我们先把所有的按钮背景颜色去掉  干掉所有人
                for (var i = 0; i < btns.length; i++) {
                    btns[i].style.backgroundColor = '';
                }
                // (2) 然后才让当前的元素背景颜色为pink 留下我自己
                this.style.backgroundColor = 'pink';

            }
        }
    </script>
```



## 1.2 案例：百度换肤

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131201.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131225.png)

```html

<style>
	.baidu {
		display: block;
		width: 620px;
		margin: 2px auto;
	}
	.baidu img {
		width: 150px;
		margin: 0 auto;
	}
	.baidu li {
		display: inline-block;
		list-style: none;
		
	}
	body {
		background-image: url(./images/1.jpg);
	}
</style>

<body>
    <ul class="baidu">
        <li><img src="images/1.jpg"></li>
        <li><img src="images/2.jpg"></li>
        <li><img src="images/3.jpg"></li>
        <li><img src="images/4.jpg"></li>
    </ul>
    <script>
        // 1. 获取元素 
        var imgs = document.querySelector('.baidu').querySelectorAll('img');
        // console.log(imgs);
        // 2. 循环注册事件 
        for (var i = 0; i < imgs.length; i++) {
            imgs[i].onclick = function() {
                // this.src 就是我们点击图片的路径   images/2.jpg
                // console.log(this.src);
                // 把这个路径 this.src 给body 就可以了
                document.body.style.backgroundImage = 'url(' + this.src + ')';
            }
        }
    </script>
</body>
```

## 1.3 案例：表格隔行变色

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131246.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131267.png)

```js
    <script>
        // 1.获取元素 获取的是 tbody 里面所有的行
        var trs = document.querySelector('tbody').querySelectorAll('tr');
        // 2. 利用循环绑定注册事件
        for (var i = 0; i < trs.length; i++) {
            // 3. 鼠标经过事件 onmouseover
            trs[i].onmouseover = function() {
                    // console.log(11);
                    this.className = 'bg';
                }
                // 4. 鼠标离开事件 onmouseout
            trs[i].onmouseout = function() {
                this.className = '';
            }
        }
    </script>
```

## 1.4 案例：全选

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131289.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131311.png)

```js
    <script>
        // 1. 全选和取消全选做法：  让下面所有复选框的checked属性（选中状态） 跟随 全选按钮即可
        // 获取元素
        
        var j_cbAll = document.getElementById('j_cbAll'); 
        var j_tbs = document.getElementById('j_tb').getElementsByTagName('input'); 
        // 全选按钮注册事件
        j_cbAll.onclick = function() {
                // this.checked 当前复选框的选中状态
                console.log(this.checked);
                for (var i = 0; i < j_tbs.length; i++) {
                    j_tbs[i].checked = this.checked;
                }
         }
         // 给所有的子复选框注册单击事件
        for (var i = 0; i < j_tbs.length; i++) {
            j_tbs[i].onclick = function() {
                // flag 控制全选按钮是否选中
                var flag = true;
                // 每次点击下面的复选框都要循环检查者4个小按钮是否全被选中
                for (var i = 0; i < j_tbs.length; i++) {
                    if (!j_tbs[i].checked) {
                        flag = false;
                        break; 
                    }
                }
                // 设置全选按钮的状态
                j_cbAll.checked = flag;
            }
        }
    </script>
```



## 1.5. 自定义属性操作

### 1.5.1 获取属性值

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131331.png)

```js
    <div id="demo" index="1" class="nav"></div>
    <script>
        var div = document.querySelector('div');
        // 1. 获取元素的属性值
        // (1) element.属性
        console.log(div.id);
        //(2) element.getAttribute('属性')  get得到获取 attribute 属性的意思 我们程序员自己添加的属性我们称为自定义属性 index
        console.log(div.getAttribute('id'));
        console.log(div.getAttribute('index'));
	</script>
```

>区别
>第一个是只能获取内置的属性比如说id，type啦，value拉什么的，第二个是可以获得我们程序员自己添加的属性，我们可以随便命名




### 1.5.2. 设置属性值

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131354.png)

```js
        // 2. 设置元素属性值
        // (1) element.属性= '值'
        div.id = 'test';
        div.className = 'navs';
        // (2) element.setAttribute('属性', '值');  主要针对于自定义属性
        div.setAttribute('index', 2);
        div.setAttribute('class', 'footer'); // class 特殊  这里面写的就是
```



### 1.5.3. 移出属性

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131376.png)

```js
		// class 不是className
        // 3 移除属性 removeAttribute(属性)    
        div.removeAttribute('index');
```

常规的直接写就是获取值，然后等于号就是赋值
对于我们自定义的set就是赋值，get就是获取值，remove就是移除值

### 1.5.4. 案例：tab栏

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131397.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131421.png)

```js
    <script>
        // 获取元素
        var tab_list = document.querySelector('.tab_list');
        var lis = tab_list.querySelectorAll('li');
        var items = document.querySelectorAll('.item');
        // for循环，给选项卡绑定点击事件
        for (var i = 0; i < lis.length; i++) {
            // 开始给5个小li 设置索引号 
            lis[i].setAttribute('index', i);
            lis[i].onclick = function() {
                // 1. 上的模块选项卡，当前这一个底色会是红色，其余不变（排他思想）
                // 干掉所有人 其余的li清除 class 这个类
                for (var i = 0; i < lis.length; i++) {
                    lis[i].className = '';
                }
                // 留下我自己 
                this.className = 'current';
                // 2. 下面的显示内容模块
                var index = this.getAttribute('index');
                console.log(index);
                // 干掉所有人 让其余的item 这些div 隐藏
                for (var i = 0; i < items.length; i++) {
                    items[i].style.display = 'none';
                }
                // 留下我自己 让对应的item 显示出来
                items[index].style.display = 'block';
            }
        }
    </script>
```



### 1.5.5. H5自定义属性

自定义属性目的：是为了保存并使用数据。有些数据可以保存到页面中而不用保存到数据库中。

自定义属性获取是通过getAttribute(‘属性’) 获取。

但是有些自定义属性很容易引起歧义，不容易判断是元素的内置属性还是自定义属性。

H5给我们新增了自定义属性：

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131445.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131467.png)

```js
    <div getTime="20" data-index="2" data-list-name="andy"></div>
    <script>
        var div = document.querySelector('div');
        // console.log(div.getTime);
        console.log(div.getAttribute('getTime'));
        div.setAttribute('data-time', 20);
        console.log(div.getAttribute('data-index'));
        console.log(div.getAttribute('data-list-name'));
        // h5新增的获取自定义属性的方法 它只能获取data-开头的
        // dataset 是一个集合里面存放了所有以data开头的自定义属性
        console.log(div.dataset);
        console.log(div.dataset.index);
        console.log(div.dataset['index']);
        // 如果自定义属性里面有多个-链接的单词，我们获取的时候采取 驼峰命名法
        console.log(div.dataset.listName);
        console.log(div.dataset['listName']);
    </script>
```

>dateset是一个集合里面存放了所有以data开头的自定义属性

## 1.6. 节点操作

### 1.6.1. 节点概述

​	网页中的所有内容都是节点（标签、属性、文本、注释等），在DOM 中，节点使用 node 来表示。

​	HTML DOM 树中的所有节点均可通过 JavaScript 进行访问，所有 HTML 元素（节点）均可被修改，也可以创建或删除。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131490.png)

​	一般地，节点至少拥有nodeType（节点类型）、nodeName（节点名称）和nodeValue（节点值）这三个基本属性。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131512.png)

**节点操作比较简单**

### 1.6.2. 节点层级

​	利用 DOM 树可以把节点划分为不同的层级关系，常见的是**父子兄层级关系**。

​    ![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131533.png)

html就是父亲,body和head就是孩子,这个是我们网页中最常见的关系,称为父子关系

### 1.6.3. 父级节点

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131553.png)

我们先找到一个节点,然后通过parentNode可以直接返回父亲节点

==以前的做法和现在的简单做法对比==
```js
    <div class="demo">
        <div class="box">
            <span class="erweima">×</span>
        </div>
    </div>
    <script>
        // 1. 父节点 parentNode
        var erweima = document.querySelector('.erweima');
        // var box = document.querySelector('.box');
        // 得到的是离元素最近的父级节点(亲爸爸) 如果找不到父节点就返回为 null
        console.log(erweima.parentNode);
    </script>
```

### 1.6.4. 子节点

**所有子节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131575.png)

**子元素节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131599.png)

```js
    <ul>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
        <li>我是li</li>
    </ul>
    <script>
        // DOM 提供的方法（API）获取
        var ul = document.querySelector('ul');
        var lis = ul.querySelectorAll('li');
        // 1. 子节点  childNodes 所有的子节点 包含 元素节点 文本节点等等
        console.log(ul.childNodes);
        console.log(ul.childNodes[0].nodeType);
        console.log(ul.childNodes[1].nodeType);
        // 2. children 获取所有的子元素节点 也是我们实际开发常用的
        console.log(ul.children);
    </script>
```

**第1个子节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131621.png)

**最后1个子节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131642.png)

**第1个子元素节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131664.png)

**最后1个子元素节点**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131687.png)

​	实际开发中，firstChild 和 lastChild 包含其他节点==比如说换行节点,这个换行节点,可能是标签附带的比如说,li标签==，操作不方便，而 firstElementChild 和 lastElementChild 又有兼容性问题，那么我们如何获取第一个子元素节点或最后一个子元素节点呢？

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131710.png)

==这个最后一个节点的需要我们去注意，之前的节点是需要版本比较高的浏览器才可以使用==

```js
    <ol>
        <li>我是li1</li>
        <li>我是li2</li>
        <li>我是li3</li>
        <li>我是li4</li>
        <li>我是li5</li>
    </ol>
    <script>
        var ol = document.querySelector('ol');
        // 1. firstChild 第一个子节点 不管是文本节点还是元素节点
        console.log(ol.firstChild);
        console.log(ol.lastChild);
        // 2. firstElementChild 返回第一个子元素节点 ie9才支持
        console.log(ol.firstElementChild);
        console.log(ol.lastElementChild);
        // 3. 实际开发的写法  既没有兼容性问题又返回第一个子元素
        console.log(ol.children[0]);
        console.log(ol.children[ol.children.length - 1]);
    </script>
```

注意:返回值里面包含了所有的子节点，包括元素节点、文本节点等
如果只想要获得里面的元素节点，则需要专门处理。所以我们一般不提倡使用childNodes

==// 3. 实际开发的写法  既没有兼容性问题又返回第一个子元素==
这个children()是不在标准里,但是浏览器确实支持的,我们经常使用的是这个


### 1.6.5. 案例：新浪下拉菜单



![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131732.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131754.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131777.png)

```js
    <script>
        // 1. 获取元素
        var nav = document.querySelector('.nav');
        var lis = nav.children; // 得到4个小li
        // 2.循环注册事件
        for (var i = 0; i < lis.length; i++) {
            lis[i].onmouseover = function() {
                this.children[1].style.display = 'block';
            }
            lis[i].onmouseout = function() {
                this.children[1].style.display = 'none';
            }
        }
    </script>
```

> 完整代码

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}

			li {
				list-style-type: none;
			}

			a {
				text-decoration: none;
				font-size: 14px;
			}

			.nav {
				margin: 100px;
			}

			.nav > li {
				position: relative;
				float: left;
				width: 80px;
				height: 41px;
				text-align: center;
			}

			.nav li a {
				display: block;
				width: 100%;
				height: 100%;
				line-height: 41px;
				color: #333;
			}

			.nav > li > a:hover {
				background-color: #eee;
			}

			.nav ul {
				display: none;
				position: absolute;
				top: 41px;
				left: 0;
				width: 100%;
				border-left: 1px solid #fecc5b;
				border-right: 1px solid #fecc5b;
			}

			.nav ul li {
				border-bottom: 1px solid #fecc5b;
			}

			.nav ul li a:hover {
				background-color: #fff5da;
			}
		</style>
	</head>
	<body>
		<ul class="nav">
			<li>
				<a href="#">微博</a>
				<ul>
					<li>
						<a href="">私信</a>
					</li>
					<li>
						<a href="">评论</a>
					</li>
					<li>
						<a href="">@我</a>
					</li>
				</ul>
			</li>
			<li>
				<a href="#">微博</a>
				<ul>
					<li>
						<a href="">私信</a>
					</li>
					<li>
						<a href="">评论</a>
					</li>
					<li>
						<a href="">@我</a>
					</li>
				</ul>
			</li>
			<li>
				<a href="#">微博</a>
				<ul>
					<li>
						<a href="">私信</a>
					</li>
					<li>
						<a href="">评论</a>
					</li>
					<li>
						<a href="">@我</a>
					</li>
				</ul>
			</li>
			<li>
				<a href="#">微博</a>
				<ul>
					<li>
						<a href="">私信</a>
					</li>
					<li>
						<a href="">评论</a>
					</li>
					<li>
						<a href="">@我</a>
					</li>
				</ul>
			</li>
		</ul>
		<script>
			var nav = document.querySelector('.nav');
			var lis = nav.children; //得到nav的四个孩子li,li里面又有四个孙子li
			for (var i = 0; i < lis.length; i++) {
				lis[i].onmouseover = function () {
					this.children[1].style.display = 'block'; //第0个是a,第二个是ul让ul进行显示
				};
				lis[i].onmouseout = function () {
					this.children[1].style.display = 'none';
				};
			}
		</script>
	</body>
</html>

```

### 1.6.6. 兄弟节点

**下一个兄弟节点**

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301201049796.png)

这个得到的是相邻的所有节点,包括元素节点和文本节点


```js
    <div>我是div</div>
    <span>我是span</span>
    <script>
        var div = document.querySelector('div');
        // 1.nextSibling 下一个兄弟节点 包含元素节点或者 文本节点等等
        console.log(div.nextSibling);
        console.log(div.previousSibling);
        // 2. nextElementSibling 得到下一个兄弟元素节点
        console.log(div.nextElementSibling);
        console.log(div.previousElementSibling);
    </script>
```

> 相邻元素节点getNextElementSibling(element)

```js
   function getNextElementSibling(element) {
      var el = element;
      while (el = el.nextSibling) {
        if (el.nodeType === 1) {
            return el;
        }
      }
      return null;
    }  
```

==所有快捷好用的操作对于旧版本的浏览器都是不支持的==

### 1.6.7. 创建节点

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131801.png)

==你单纯创建是没有用的,只有当你添加到页面中才有用,所以引入我们能的添加节点==

### 1.6.8. 添加节点

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131824.png)

==node就是获取的父亲节点的对象,然后这个是只能在父亲节点的后面添加==

==before,这个可以在父亲节点的子节点的前面添加,不过这个,我们是要指定元素前面尽心添加==



```js
    <ul>
        <li>123</li>
    </ul>
    <script>
        // 1. 创建节点元素节点
        var li = document.createElement('li');
        // 2. 添加节点 node.appendChild(child)  node 父级  child 是子级 后面追加元素
        var ul = document.querySelector('ul');
        ul.appendChild(li);
        // 3. 添加节点 node.insertBefore(child, 指定元素);
        var lili = document.createElement('li');
        ul.insertBefore(lili, ul.children[0]);
        // 4. 我们想要页面添加一个新的元素 ： 1. 创建元素 2. 添加元素
    </script>
```

### 1.6.9. 案例：简单版发布留言

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131848.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151131870.png)

```js
<body>
    <textarea name="" id=""></textarea>
    <button>发布</button>
    <ul>

    </ul>
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value;
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
            }
        }
    </script>
</body>
```

==完全代码==
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
        
        body {
            padding: 100px;
        }
        
        textarea {
            width: 200px;
            height: 100px;
            border: 1px solid pink;
            outline: none;
            resize: none;
        }
        
        ul {
            margin-top: 50px;
        }
        
        li {
            width: 300px;
            padding: 5px;
            background-color: rgb(245, 209, 243);
            color: red;
            font-size: 14px;
            margin: 15px 0;
        }
    </style>
</head>
<body>
    <textarea name="" id=""></textarea>
    <button>发布</button>
    <ul>

    </ul>
    <script>
        var btn = document.querySelector('button');
        var ul =document.querySelector('ul');
        var text= document.querySelector('textarea');
        //  动态创建一个li
        btn.onclick= function(){
            if(text.value==''){
                alert('你没有输入内容');
            }else {
                var li = document.createElement('li');
                li.innerText=text.value;
                // ul.appendChild(li);
                ul.insertBefore(li,ul.children[0]);
                text.value='';
            }
        }
    </script>
</body>
</html>
```

# 节点操作/DOM/事件总结/鼠标事件

> 学习目标：
>
> 能够使用removeChild()方法删除节点
>
> 能够完成动态生成表格案例
>
> 能够使用传统方式和监听方式给元素注册事件
>
> 能够说出事件流执行的三个阶段
>
> 能够在事件处理函数中获取事件对象
>
> 能够使用事件对象取消默认行为
>
> 能够使用事件对象阻止事件冒泡
>
> 能够使用事件对象获取鼠标的位置
>
> 能够完成跟随鼠标的天使案例

## 1.1. 节点操作

### 1.1.1 删除节点

node.removeChild() 方法从 node节点中删除一个子节点，返回删除的节点。

```js
    <button>删除</button>
    <ul>
        <li>熊大</li>
        <li>熊二</li>
        <li>光头强</li>
    </ul>
    <script>
        // 1.获取元素
        var ul = document.querySelector('ul');
        var btn = document.querySelector('button');
        // 2. 删除元素  node.removeChild(child)
        // ul.removeChild(ul.children[0]);
        // 3. 点击按钮依次删除里面的孩子
        btn.onclick = function() {
            if (ul.children.length == 0) {
                this.disabled = true;
            } else {
                ul.removeChild(ul.children[0]);
            }
        }
    </script>
```
> 	this.disabled的作用是禁用按钮的操作

==可以删除父节点的任意子节点==

### 1.1.2 案例：删除留言

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301201152569.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132006.png)

```js
    <textarea name="" id=""></textarea>
    <button>发布</button>
    <ul>

    </ul>
    <script>
        // 1. 获取元素
        var btn = document.querySelector('button');
        var text = document.querySelector('textarea');
        var ul = document.querySelector('ul');
        // 2. 注册事件
        btn.onclick = function() {
            if (text.value == '') {
                alert('您没有输入内容');
                return false;
            } else {
                // console.log(text.value);
                // (1) 创建元素
                var li = document.createElement('li');
                // 先有li 才能赋值
                li.innerHTML = text.value + "<a href='javascript:;'>删除</a>";
                // (2) 添加元素
                // ul.appendChild(li);
                ul.insertBefore(li, ul.children[0]);
                // (3) 删除元素 删除的是当前链接的li  它的父亲
                var as = document.querySelectorAll('a');
                for (var i = 0; i < as.length; i++) {
                    as[i].onclick = function() {
                        // 删除的是 li 当前a所在的li  this.parentNode;
                        ul.removeChild(this.parentNode);
                    }
                }
            }
        }
    </script>
```

### 1.1.3 复制（克隆）节点

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132032.png)

```js
    <ul>
        <li>1111</li>
        <li>2</li>
        <li>3</li>
    </ul>
    <script>
        var ul = document.querySelector('ul');
        // 1. node.cloneNode(); 括号为空或者里面是false 浅拷贝 只复制标签不复制里面的内容
        // 2. node.cloneNode(true); 括号为true 深拷贝 复制标签复制里面的内容
        var lili = ul.children[0].cloneNode(true);
        ul.appendChild(lili);
    </script>
```

### 1.1.4 案例：动态生成表格

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132052.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132072.png)

```js
    <script>
        // 1.先去准备好学生的数据
        var datas = [{
            name: '魏璎珞',
            subject: 'JavaScript',
            score: 100
        }, {
            name: '弘历',
            subject: 'JavaScript',
            score: 98
        }, {
            name: '傅恒',
            subject: 'JavaScript',
            score: 99
        }, {
            name: '明玉',
            subject: 'JavaScript',
            score: 88
        }, {
            name: '大猪蹄子',
            subject: 'JavaScript',
            score: 0
        }];
        // 2. 往tbody 里面创建行： 有几个人（通过数组的长度）我们就创建几行
        var tbody = document.querySelector('tbody');
		// 遍历数组
        for (var i = 0; i < datas.length; i++) { 
            // 1. 创建 tr行
            var tr = document.createElement('tr');
            tbody.appendChild(tr);
            // 2. 行里面创建单元格td 单元格的数量取决于每个对象里面的属性个数  
            // 使用for in遍历学生对象
            for (var k in datas[i]) { 
                // 创建单元格 
                var td = document.createElement('td');
                // 把对象里面的属性值 datas[i][k] 给 td  
                td.innerHTML = datas[i][k];
                tr.appendChild(td);
            }
            // 3. 创建有删除2个字的单元格 
            var td = document.createElement('td');
            td.innerHTML = '<a href="javascript:;">删除 </a>';
            tr.appendChild(td);

        }
        // 4. 删除操作 开始 
        var as = document.querySelectorAll('a');
        for (var i = 0; i < as.length; i++) {
            as[i].onclick = function() {
                // 点击a 删除 当前a 所在的行(链接的爸爸的爸爸)  node.removeChild(child)  
                tbody.removeChild(this.parentNode.parentNode)
            }
        }
    </script>
```



### 1.1.5 创建元素的三种方式

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132092.png)

> document.write会将页面中的内容进行清除

```js
    <script>
        // 三种创建元素方式区别 
        // 1. document.write() 创建元素  如果页面文档流加载完毕，再调用这句话会导致页面重绘
         var btn = document.querySelector('button');
         btn.onclick = function() {
             document.write('<div>123</div>');
         }

        // 2. innerHTML 创建元素
        var inner = document.querySelector('.inner');
         for (var i = 0; i <= 100; i++) {
             inner.innerHTML += '<a href="#">百度</a>'
         }
        var arr = [];
        for (var i = 0; i <= 100; i++) {
            arr.push('<a href="#">百度</a>');
        }
        inner.innerHTML = arr.join('');
        // 3. document.createElement() 创建元素
        var create = document.querySelector('.create');
        for (var i = 0; i <= 100; i++) {
            var a = document.createElement('a');
            create.appendChild(a);
        }
    </script>
```



### 1.1.6 innerTHML和createElement效率对比

**innerHTML字符串拼接方式（效率低）**

```js
<script>
    function fn() {
        var d1 = +new Date();
        var str = '';
        for (var i = 0; i < 1000; i++) {
            document.body.innerHTML += '<div style="width:100px; height:2px; border:1px solid blue;"></div>';
        }
        var d2 = +new Date();
        console.log(d2 - d1);
    }
    fn();
</script>
```

**createElement方式（效率一般）**

```js
<script>
    function fn() {
        var d1 = +new Date();

        for (var i = 0; i < 1000; i++) {
            var div = document.createElement('div');
            div.style.width = '100px';
            div.style.height = '2px';
            div.style.border = '1px solid red';
            document.body.appendChild(div);
        }
        var d2 = +new Date();
        console.log(d2 - d1);
    }
    fn();
</script>
```

**innerHTML数组方式（效率高）**

```js
<script>
    function fn() {
        var d1 = +new Date();
        var array = [];
        for (var i = 0; i < 1000; i++) {
            array.push('<div style="width:100px; height:2px; border:1px solid blue;"></div>');
        }
        document.body.innerHTML = array.join('');
        var d2 = +new Date();
        console.log(d2 - d1);
    }
    fn();
</script>
```

==总结==
由于字符串的特性,我们采用innerHTML进行字符串拼接的方法是最费时的,但是当我们使用数组的方法来说innerHTML的方法就是最快速的


## 1.2. DOM的核心总结

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132114.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132136.png)



关于dom操作，我们主要针对于元素的操作。主要有创建、增、删、改、查、属性操作、事件操作。

### 1.2.1. 创建

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132158.png)

### 1.2.2. 增加

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132181.png)

### 1.2.3. 删

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132203.png)

### 1.2.4. 改

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132225.png)

### 1.2.5. 查

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132247.png)


### 1.2.6. 属性操作

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132270.png)

### 1.2.7. 事件操作（重点）



## 1.3. 事件高级

### 1.3.1. 注册事件（2种方式）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132293.png)

传统注册方式就是一个元素只能有一个事件,只能有一个function,事件具有唯一性
后一个方式可以注册多个事件,当触发的时候是同时执行的,比如说可以注册两个onclick事件,点击一下,两个事件是同时执行的

### 1.3.2 事件监听

#### addEventListener()事件监听（IE9以后支持）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132316.png)

eventTarget.addEventListener()方法将指定的监听器注册到 eventTarget（目标对象）上，当该对象触发指定的事件时，就会执行事件处理函数。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132338.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301202103911.png)


> 一个常见的写法是
> btn[i].addEventListener('click' ,  function(){
> 		alert(' ')
> })
> 和看上去不太一样

#### attacheEvent()事件监听（IE678支持）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132360.png)

​	eventTarget.attachEvent()方法将指定的监听器注册到 eventTarget（目标对象） 上，当该对象触发指定的事件时，指定的回调函数就会被执行。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132384.png)

```js
<button>传统注册事件</button>
<button>方法监听注册事件</button>
<button>ie9 attachEvent</button>
<script>
    var btns = document.querySelectorAll('button');
    // 1. 传统方式注册事件
    btns[0].onclick = function() {
        alert('hi');
    }
    btns[0].onclick = function() {
            alert('hao a u');
        }
   // 2. 事件侦听注册事件 addEventListener 
   // (1) 里面的事件类型是字符串 必定加引号 而且不带on
   // (2) 同一个元素 同一个事件可以添加多个侦听器（事件处理程序）
    btns[1].addEventListener('click', function() {
        alert(22);
    })
    btns[1].addEventListener('click', function() {
            alert(33);
    })
    // 3. attachEvent ie9以前的版本支持
    btns[2].attachEvent('onclick', function() {
        alert(11);
    })
</script>
```

==这个attachEvent兼容性太差了==



#### 事件监听兼容性解决方案

封装一个函数，函数中判断浏览器的类型：

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132407.png)

### 1.3.3. 删除事件（解绑事件）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132432.png)

**对于我们来说有些时间我们只希望能够执行一次,比如说弹出框,这个我们希望只能执行一次**

对于这个监听方法的操作我们不能用匿名的函数事件

```js
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <script>
        var divs = document.querySelectorAll('div');
        divs[0].onclick = function() {
            alert(11);
            // 1. 传统方式删除事件
            divs[0].onclick = null;
        }
        // 2. removeEventListener 删除事件
        divs[1].addEventListener('click', fn) // 里面的fn 不需要调用加小括号
        function fn() {
            alert(22);
            divs[1].removeEventListener('click', fn);
        }
        // 3. detachEvent
        divs[2].attachEvent('onclick', fn1);

        function fn1() {
            alert(33);
            divs[2].detachEvent('onclick', fn1);
        }
    </script>
```

**删除事件兼容性解决方案**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132456.png)

==初学者不用担心==

### 1.3.4. DOM事件流

==它的意义就是让你知道浏览器的对象执行过程,对于事件来说,不是无缘无故的执行的,而是通过一种顺序执行的,我们常见的是冒泡,从下往上执行,当子元素和父元素有相同的事件的时候,这样的话可能点击下面的事件,上面的事件也会执行了==


> html中的标签都是相互嵌套的，我们可以将元素想象成一个盒子装一个盒子，document是最外面的大盒子。
> 当你单击一个div时，同时你也单击了div的父元素，甚至整个页面。
> 
> 那么是先执行父元素的单击事件，还是先执行div的单击事件 ？？？

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132481.png)

> 比如：我们给页面中的一个div注册了单击事件，当你单击了div时，也就单击了body，单击了html，单击了document。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132506.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132531.png)

 ```
当时的2大浏览器霸主谁也不服谁！
IE 提出从目标元素开始，然后一层一层向外接收事件并响应，也就是冒泡型事件流。
Netscape（网景公司）提出从最外层开始，然后一层一层向内接收事件并响应，也就是捕获型事件流。
江湖纷争，武林盟主也脑壳疼！！！
最终，w3c 采用折中的方式，平息了战火，制定了统一的标准 —--— 先捕获再冒泡。
现代浏览器都遵循了此标准，所以当事件发生时，会经历3个阶段。
 ```

DOM 事件流会经历3个阶段： 

1. 捕获阶段

2. 当前目标阶段

3. 冒泡阶段 

​	我们向水里面扔一块石头，首先它会有一个下降的过程，这个过程就可以理解为从最顶层向事件发生的最具体元素（目标点）的捕获过程；之后会产生泡泡，会在最低点（ 最具体元素）之后漂浮到水面上，这个过程相当于事件冒泡。 

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132557.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132581.png)

**事件冒泡**



```js
    <div class="father">
        <div class="son">son盒子</div>
    </div>
    <script>
        // onclick 和 attachEvent（ie） 在冒泡阶段触发
        // 冒泡阶段 如果addEventListener 第三个参数是 false 或者 省略 
        // son -> father ->body -> html -> document
        var son = document.querySelector('.son');
		// 给son注册单击事件
        son.addEventListener('click', function() {
            alert('son');
        }, false);
		// 给father注册单击事件
        var father = document.querySelector('.father');
        father.addEventListener('click', function() {
            alert('father');
        }, false);
		// 给document注册单击事件，省略第3个参数
        document.addEventListener('click', function() {
            alert('document');
        })
    </script>
```

**事件捕获**
对于addEventListener其中它的第三个参数如果为true,表示在事件捕获阶段调用事件处理程序,不会参与冒泡,无法从下到上的获取对象,事件是从上到下执行的

```js
    <div class="father">
        <div class="son">son盒子</div>
    </div>
    <script>
        // 如果addEventListener() 第三个参数是 true 那么在捕获阶段触发
        // document -> html -> body -> father -> son
         var son = document.querySelector('.son');
		// 给son注册单击事件，第3个参数为true
         son.addEventListener('click', function() {
             alert('son');
         }, true);
         var father = document.querySelector('.father');
		// 给father注册单击事件，第3个参数为true
         father.addEventListener('click', function() {
             alert('father');
         }, true);
		// 给document注册单击事件，第3个参数为true
        document.addEventListener('click', function() {
            alert('document');
        }, true)
    </script>
```

### 1.3.5. 事件对象

#### 什么是事件对象

事件发生后，跟事件相关的一系列信息数据的集合都放到这个对象里面，这个对象就是事件对象。

比如：  

1. 谁绑定了这个事件。

2. 鼠标触发事件的话，会得到鼠标的相关信息，如鼠标位置。

3. 键盘触发事件的话，会得到键盘的相关信息，如按了哪个键。

#### 事件对象的使用

事件触发发生时就会产生事件对象，并且系统会以实参的形式传给事件处理函数。

所以，在事件处理函数中声明1个形参用来接收事件对象。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132605.png)

#### 事件对象的兼容性处理

事件对象本身的获取存在兼容问题：

1. 标准浏览器中是浏览器给方法传递的参数，只需要定义形参 e 就可以获取到。

2. 在 IE6~8 中，浏览器不会给方法传递参数，如果需要的话，需要到 window.event 中获取查找。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132630.png)

```
只要“||”前面为false, 不管“||”后面是true 还是 false，都返回 “||” 后面的值。
只要“||”前面为true, 不管“||”后面是true 还是 false，都返回 “||” 前面的值。
```

```js
    <div>123</div>
    <script>
        var div = document.querySelector('div');
        div.onclick = function(e) {
                // 事件对象
                e = e || window.event;
                console.log(e);
        }
    </script>
```

#### 事件对象的属性和方法

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132655.png)

#### e.target 和 this 的区别

-  this 是事件绑定的元素（绑定这个事件处理函数的元素） 。

-  e.target 是事件触发的元素。

常情况下terget 和 this是一致的，
但有一种情况不同，那就是在事件冒泡时（父子元素有相同事件，单击子元素，父元素的事件处理函数也会被触发执行），
这时候this指向的是父元素，因为它是绑定事件的元素对象，
而target指向的是子元素，因为他是触发事件的那个具体元素对象。 ```


```js
    <div>123</div>
    <script>
        var div = document.querySelector('div');
        div.addEventListener('click', function(e) {
            // e.target 和 this指向的都是div
            console.log(e.target);
            console.log(this);

        });
    </script>
```

事件冒泡下的e.target和this

```js
    <ul>
        <li>abc</li>
        <li>abc</li>
        <li>abc</li>
    </ul>
    <script>
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
              // 我们给ul 绑定了事件  那么this 就指向ul  
              console.log(this); // ul

              // e.target 触发了事件的对象 我们点击的是li e.target 指向的就是li
              console.log(e.target); // li
        });
    </script>
```

### 1.3.6 阻止默认行为

> html中一些标签有默认行为，例如a标签被单击后，默认会进行页面跳转。a标签的默认行为就是跳转效果,提交按钮的默认效果就是提交

```js
    <a href="http://www.baidu.com">百度</a>
    <script>
        // 2. 阻止默认行为 让链接不跳转 
        var a = document.querySelector('a');
        a.addEventListener('click', function(e) {
             e.preventDefault(); //  dom 标准写法
        });
        // 3. 传统的注册方式
        a.onclick = function(e) {
            // 普通浏览器 e.preventDefault();  方法
            e.preventDefault();
            // 低版本浏览器 ie678  returnValue  属性
            e.returnValue = false;
            // 我们可以利用return false 也能阻止默认行为 没有兼容性问题
            return false;
        }
    </script>
```

### 1.3.7 阻止事件冒泡

事件冒泡本身的特性，会带来的坏处，也会带来的好处。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132680.png)

直接使用这个方法就好了,利用这个方法可以直接阻止冒泡

```js
    <div class="father">
        <div class="son">son儿子</div>
    </div>
    <script>
        var son = document.querySelector('.son');
		// 给son注册单击事件
        son.addEventListener('click', function(e) {
            alert('son');
            e.stopPropagation(); // stop 停止  Propagation 传播
            window.event.cancelBubble = true; // 非标准 cancel 取消 bubble 泡泡
        }, false);

        var father = document.querySelector('.father');
		// 给father注册单击事件
        father.addEventListener('click', function() {
            alert('father');
        }, false);
		// 给document注册单击事件
        document.addEventListener('click', function() {
            alert('document');
        })
    </script>
```

**阻止事件冒泡的兼容性处理**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132703.png)

### 1.3.8 事件委托

事件冒泡本身的特性，会带来的坏处，也会带来的好处。

#### 什么是事件委托

```
把事情委托给别人，代为处理。
```

事件委托也称为事件代理，在 jQuery 里面称为事件委派。

> 说白了就是，不给子元素注册事件，给父元素注册事件，把处理代码在父元素的事件中执行。



**生活中的代理：**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132727.png)

**js事件中的代理：**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132749.png)

#### 事件委托的原理

​	给父元素注册事件，利用事件冒泡，当子元素的事件触发，会冒泡到父元素，然后去控制相应的子元素。

#### 事件委托的作用

- 我们只操作了一次 DOM ，提高了程序的性能。

- 动态新创建的子元素，也拥有事件。

```js
    <ul>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
        <li>知否知否，点我应有弹框在手！</li>
    </ul>
    <script>
        // 事件委托的核心原理：给父节点添加侦听器， 利用事件冒泡影响每一个子节点
        var ul = document.querySelector('ul');
        ul.addEventListener('click', function(e) {
            // e.target 这个可以得到我们点击的对象
            e.target.style.backgroundColor = 'pink';
        })
    </script>
```

## 1.4. 常用鼠标事件

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132771.png)

### 1.4.1 案例：禁止选中文字和禁止右键菜单

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132797.png)

```js
<body>
    我是一段不愿意分享的文字
    <script>
        // 1. contextmenu 我们可以禁用右键菜单
        document.addEventListener('contextmenu', function(e) {
                e.preventDefault();
        })
        // 2. 禁止选中文字 selectstart
        document.addEventListener('selectstart', function(e) {
            e.preventDefault();
        })
    </script>
</body>
```

### 1.4.2 鼠标事件对象

其中clientX和clientY是鼠标事件的对象相对于浏览器可视区域的X和Y坐标,但是对于一些比较大的浏览器窗口,比如说带有滚动条的浏览器窗口的下面的元素,,如果想要知道,其距离浏览器网页文档最上面的距离,就不能用这个.

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132821.png)

### 1.4.3 获取鼠标在页面的坐标

```js
    <script>
        // 鼠标事件对象 MouseEvent
        document.addEventListener('click', function(e) {
            // 1. client 鼠标在可视区的x和y坐标
            console.log(e.clientX);
            console.log(e.clientY);
            console.log('---------------------');

            // 2. page 鼠标在页面文档的x和y坐标
            console.log(e.pageX);
            console.log(e.pageY);
            console.log('---------------------');

            // 3. screen 鼠标在电脑屏幕的x和y坐标
            console.log(e.screenX);
            console.log(e.screenY);

        })
    </script>
```

### 1.4.4 案例：跟随鼠标的天使

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132844.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151132868.png)

```js
    <img src="images/angel.gif" alt="">
    <script>
        var pic = document.querySelector('img');
        document.addEventListener('mousemove', function(e) {
        	// 1. mousemove只要我们鼠标移动1px 就会触发这个事件
        	// 2.核心原理： 每次鼠标移动，我们都会获得最新的鼠标坐标， 
            // 把这个x和y坐标做为图片的top和left 值就可以移动图片
        	var x = e.pageX;
        	var y = e.pageY;
        	console.log('x坐标是' + x, 'y坐标是' + y);
        	//3 . 千万不要忘记给left 和top 添加px 单位
        	pic.style.left = x - 50 + 'px';
        	pic.style.top = y - 40 + 'px';
    	});
    </script>
```

这个鼠标的单位一定不要少,否则的话就不要加上,而且我们要提前设置图像的css的定位为absolute

# 键盘事件/BOM/JS执行机制

> 学习目标：
>
> 能够说出常用的3-5个键盘事件
>
> 能够知道如何获取当前键盘按下的是哪个键
>
> 能够知道浏览器的顶级对象window
>
> 能够使用window.onload事件
>
> 能够使用window.onresize事件
>
> 能够说出两种定时器的区别
>
> 能够使用location对象的href属性完成页面之间的跳转
>
> 能够使用location对象获取url中的参数部分
>
> 能够使用history提供的方法实现页面刷新

## 1.1. 常用的键盘事件

### 1.1.1 键盘事件

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134585.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134608.png)

addEventListener特性不需要加on

```js
    <script>
        // 常用的键盘事件
        //1. keyup 按键弹起的时候触发 
        document.addEventListener('keyup', function() {
            console.log('我弹起了');
        })

        //3. keypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keypress', function() {
                console.log('我按下了press');
        })
        //2. keydown 按键按下的时候触发  能识别功能键 比如 ctrl shift 左右箭头啊
        document.addEventListener('keydown', function() {
                console.log('我按下了down');
        })
        // 4. 三个事件的执行顺序  keydown -- keypress -- keyup
    </script>
```

==keypress不能识别键盘上的功能键，只能识别键盘上的一些正常的按键==

### 1.1.2 键盘事件对象

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134637.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134658.png)

**使用keyCode属性判断用户按下哪个键**

其中特殊字符不能通过kerpress读取,但是特殊字符可以通过keyup,和keydown读取,其中特数字符也是有ASCII码的

```js
    <script>
        // 键盘事件对象中的keyCode属性可以得到相应键的ASCII码值
        document.addEventListener('keyup', function(e) {
            console.log('up:' + e.keyCode);
            // 我们可以利用keycode返回的ASCII码值来判断用户按下了那个键
            if (e.keyCode === 65) {
                alert('您按下的a键');
            } else {
                alert('您没有按下a键')
            }
        })
        document.addEventListener('keypress', function(e) {
            // console.log(e);
            console.log('press:' + e.keyCode);
        })
    </script>
```


```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
	</head>
	<body>
		<script>
			document.addEventListener('keyup', function (e) {
				// console.log('我弹起来了');
                console.log('up:'+e.keyCode);
			});
			document.addEventListener('keydown', function (e) {
				// console.log('我按下了down');
                console.log('down:'+e.keyCode);
			});
			document.addEventListener('keypress', function (e) {
				// console.log('我按下了press');
                console.log('press:'+e.keyCode);
			});
		</script>
	</body>
</html>
```


### 1.1.3 案例：模拟京东按键输入内容

当我们按下 s 键， 光标就定位到搜索框（文本框获得焦点）。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134679.png)

> 注意：触发获得焦点事件，可以使用 元素对象.focus()

```js
    <input type="text">
    <script>
        // 获取输入框
        var search = document.querySelector('input');
		// 给document注册keyup事件
        document.addEventListener('keyup', function(e) {
            // 判断keyCode的值
            if (e.keyCode === 83) {
                // 触发输入框的获得焦点事件
                search.focus();
            }
        })
    </script>
```

### 1.1.4 案例：模拟京东快递单号查询

要求：当我们在文本框中输入内容时，文本框上面自动显示大字号的内容。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134701.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134722.png)

```js
    <div class="search">
        <div class="con">123</div>
        <input type="text" placeholder="请输入您的快递单号" class="jd">
    </div>
    <script>
        // 获取要操作的元素
        var con = document.querySelector('.con');
        var jd_input = document.querySelector('.jd');
		// 给输入框注册keyup事件
        jd_input.addEventListener('keyup', function() {
				// 判断输入框内容是否为空
                if (this.value == '') {
                    // 为空，隐藏放大提示盒子
                    con.style.display = 'none';
                } else {
                    // 不为空，显示放大提示盒子，设置盒子的内容
                    con.style.display = 'block';
                    con.innerText = this.value;
                }
            })
        // 给输入框注册失去焦点事件，隐藏放大提示盒子
        jd_input.addEventListener('blur', function() {
                con.style.display = 'none';
            })
        // 给输入框注册获得焦点事件
        jd_input.addEventListener('focus', function() {
            // 判断输入框内容是否为空
            if (this.value !== '') {
                // 不为空则显示提示盒子
                con.style.display = 'block';
            }
        })
    </script>
```

> 完整代码

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
		<style>
			* {
				margin: 0;
				padding: 0;
			}

			.search {
				position: relative;
				width: 178px;
				margin: 100px;
			}

			.con {
				display: none;
				position: absolute;
				top: -40px;
				width: 171px;
				border: 1px solid rgba(0, 0, 0, 0.2);
				box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
				padding: 5px 0;
				font-size: 18px;
				line-height: 20px;
				color: #333;
			}

			.con::before {
				content: '';
				width: 0;
				height: 0;
				position: absolute;
				top: 28px;
				left: 18px;
				border: 8px solid #000;
				border-style: solid dashed dashed;
				border-color: #fff transparent transparent;
			}
		</style>
	</head>
	<body>
		<div class="search">
			<div class="con">123</div>
			<input type="text" placeholder="请输入您的快递单号" class="jd" />
		</div>
		<script>
			var search = document.querySelector('.search');
			var con = document.querySelector('.con');
			var ipt = document.querySelector('.jd');
			// 两者的内容是一样的
			ipt.addEventListener('keyup', function () {
				if (this.value == '') {
					//为空 ,隐藏盒子
					con.style.display = 'none';
				} else {
					// 盒子不在隐藏
					con.style.display = 'block';
					// 内容一样
					con.innerText = this.value;
				}
			});
			// 焦点不在隐藏盒子
			ipt.addEventListener('blur', function () {
				con.style.display = 'none';
			});
			// 当处于聚焦状态的时候不为空显示盒子
			ipt.addEventListener('focus', function () {
				if (this.value == '') {
					con.style.display = 'none';
				} else {
					con.style.display = 'block';
				}
			});
		</script>
	</body>
</html>
```


## 1.2. BOM

### 1.2.1. 什么是BOM

​	BOM（Browser Object Model）即浏览器对象模型，它提供了独立于内容而与浏览器窗口进行交互的对象，其核心对象是 window。

​	BOM 由一系列相关的对象构成，并且每个对象都提供了很多方法与属性。

​	BOM 缺乏标准，JavaScript 语法的标准化组织是 ECMA，DOM 的标准化组织是 W3C，BOM 最初是Netscape 浏览器标准的一部分。
==BOM的标准是由浏览器所指定的，它的兼容性很差==


![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134744.png)

==就是BOM时将浏览器当作了一个对象,DOM时将浏览器的网页当做了一个对象，比如说alert这个不同的浏览器就不一样==

### 1.2.2. BOM的构成

BOM 比 DOM 更大，它包含 DOM。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134768.png)

### 1.2.3. 顶级对象window

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134791.png)

windows是最大的属性
定义的全局变量，会自动变成windows对象的属性
函数自动变成方法，通过“.”来进行调用



### 1.2.4. window对象的常见事件

#### 页面（窗口）加载事件（2种）

**第1种**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134813.png)

window.onload 是窗口 (页面）加载事件，**当文档内容完全加载完成**会触发该事件(包括图像、脚本文件、CSS 文件等), 就调用的处理函数。

当脚本文件和css文件都加载完成之后那么事件当然是可以执行的,此时脚本的位置就可以放在执行事件的上面

windows也是有事件冲突的,为了解决这个我们也是可以通过addEventListener();


![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134838.png)

**第2种**

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134862.png)

​	DOMContentLoaded 事件触发时，仅当DOM加载完成，不包括样式表，图片，flash等等。
==就是当页面中的标签已经加载完成了,此时已经可以实现交互效果了==


​	IE9以上才支持！！！

​	如果页面的图片很多的话, 从用户访问到onload触发可能需要较长的时间, 交互效果就不能实现，必然影响用户的体验，此时用 DOMContentLoaded 事件比较合适。

```js
    <script>
        window.addEventListener('load', function() {
            var btn = document.querySelector('button');
            btn.addEventListener('click', function() {
                alert('点击我');
            })
        })
        window.addEventListener('load', function() {
            alert(22);
        })
        document.addEventListener('DOMContentLoaded', function() {
            alert(33);
        })
    </script>
```

#### 调整窗口大小事件

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134885.png)

​	window.onresize 是调整窗口大小加载事件,  当触发时就调用的处理函数。

注意：

1. 只要窗口大小发生像素变化，就会触发这个事件。

2. 我们经常利用这个事件完成响应式布局。 window.innerWidth 当前屏幕的宽度

```js
    <script>
        // 注册页面加载事件
        window.addEventListener('load', function() {
            var div = document.querySelector('div');
        	// 注册调整窗口大小事件
            window.addEventListener('resize', function() {
                // window.innerWidth 获取窗口大小
                console.log('变化了');
                if (window.innerWidth <= 800) {
                    div.style.display = 'none';
                } else {
                    div.style.display = 'block';
                }
            })
        })
    </script>
    <div></div>
```



### 1.2.5. 定时器（两种）

window 对象给我们提供了 2 个非常好用的方法-定时器。

- setTimeout() 

- setInterval()  

#### setTimeout() 炸弹定时器

##### 开启定时器

window.setTimeout(调用函数，延迟的毫秒数)；

其中window可以省略
这个调用函数可以直接写函数，或者写函数名，或者采用字符串‘函数名（）’三种形式，第三种我们不推荐

延迟的毫秒数省略默认是0，如果写，必须是毫秒

因为定时器可能有很多，所以我们经常，给定时器赋值一个标识符，比如说timer1，timer2等



![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134958.png)
> 普通函数是按照代码顺序直接调用。
> 简单理解： 回调，就是回头调用的意思。上一件事干完，再回头再调用这个函数。
> 例如：定时器中的调用函数，事件处理函数，也是回调函数。
> 以前我们讲的   element.onclick = function(){}   或者  element.addEventListener(“click”, fn);   里面的 函数也是回调函数。

==这些回调函数，只有在你回来使用这些事件的时候才会触发==

```js
    <script>
        // 回调函数是一个匿名函数
         setTimeout(function() {
             console.log('时间到了');

         }, 2000);
        function callback() {
            console.log('爆炸了');
        }
		// 回调函数是一个有名函数
        var timer1 = setTimeout(callback, 3000);
        var timer2 = setTimeout(callback, 5000);
    </script>
```

##### 案例：5秒后关闭广告

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134983.png)



![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134006.png)

```html
<body>
    <img src="images/ad.jpg" alt="" class="ad">
    <script>
        // 获取要操作的元素
        var ad = document.querySelector('.ad');
		// 开启定时器
        setTimeout(function() {
            ad.style.display = 'none';
        }, 5000);
    </script>
</body>
```

##### 停止定时器

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134030.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134053.png)

```html
    <button>点击停止定时器</button>
    <script>
        var btn = document.querySelector('button');
		// 开启定时器
        var timer = setTimeout(function() {
            console.log('爆炸了');
        }, 5000);
		// 给按钮注册单击事件
        btn.addEventListener('click', function() {
            // 停止定时器
            clearTimeout(timer);
        })
    </script>
```



#### setInterval() 闹钟定时器

##### 开启定时器

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134077.png)

```js
    <script>
        // 1. setInterval 
        setInterval(function() {
            console.log('继续输出');
        }, 1000);
    </script>
```

##### 案例：倒计时

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134101.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134125.png)

```js
    <div>
        <span class="hour">1</span>
        <span class="minute">2</span>
        <span class="second">3</span>
    </div>
    <script>
        // 1. 获取元素（时分秒盒子） 
        var hour = document.querySelector('.hour'); // 小时的黑色盒子
        var minute = document.querySelector('.minute'); // 分钟的黑色盒子
        var second = document.querySelector('.second'); // 秒数的黑色盒子
        var inputTime = +new Date('2019-5-1 18:00:00'); // 返回的是用户输入时间总的毫秒数

        countDown(); // 我们先调用一次这个函数，防止第一次刷新页面有空白 

        // 2. 开启定时器
        setInterval(countDown, 1000);
		
        function countDown() {
            var nowTime = +new Date(); // 返回的是当前时间总的毫秒数
            var times = (inputTime - nowTime) / 1000; // times是剩余时间总的秒数 
            var h = parseInt(times / 60 / 60 % 24); //时
            h = h < 10 ? '0' + h : h;
            hour.innerHTML = h; // 把剩余的小时给 小时黑色盒子
            var m = parseInt(times / 60 % 60); // 分
            m = m < 10 ? '0' + m : m;
            minute.innerHTML = m;
            var s = parseInt(times % 60); // 当前的秒
            s = s < 10 ? '0' + s : s;
            second.innerHTML = s;
        }
    </script>
```

##### 停止定时器

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134150.png)

#### 案例：发送短信倒计时

​	点击按钮后，该按钮60秒之内不能再次点击，防止重复发送短信。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134175.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134199.png)

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
	</head>
	<body>
		手机号码： <input type="number" /> <button>发送</button>
		<script>
			var btn = document.querySelector('button');
			// 全局变量，定义剩下的秒数
			var time = 60;
			// 注册单击事件
			btn.addEventListener('click', function () {
				// 禁用按钮
				btn.disabled = true;
				// 开启定时器,这是一个函数,每秒钟执行一次,每次都显示剩余多长时间
				var timer = setInterval(function () {
					// 判断剩余秒数
					if (time == 0) {
						// 清除定时器和复原按钮,如果不清楚的话,这个按钮就会一直执行下去
						clearInterval(timer);
						btn.disabled = false;
						btn.innerHTML = '发送';
					} else {
						btn.innerHTML = '还剩下' + time + '秒';
						time--;
					}
				}, 1000);
			});
		</script>
	</body>
</html>
```



### 1.2.6. this指向问题

​	this的指向在函数定义的时候是确定不了的，只有函数执行的时候才能确定this到底指向谁，一般情况下this的最终指向的是那个调用它的对象。

现阶段，我们先了解一下几个this指向

1. 全局作用域或者普通函数中this指向全局对象window（注意定时器里面的this指向window）

2. 方法调用中谁调用this指向谁
3. 构造函数中this指向构造函数的实例

==总结==
- 当时全局作用域或者普通函数中this指向全局对象window，其中有一个比较特殊的就是定时器时一个函数，但是其里面的this指向的而是window
- 当是一个方法的时候，谁调用指向谁
- 当我们利用函数来创建对象的时候，这个时候this指向的就不是window了，此时指向的事创建对象的那个变量

```js
    <button>点击</button>
    <script>
        // this 指向问题 一般情况下this的最终指向的是那个调用它的对象
        // 1. 全局作用域或者普通函数中this指向全局对象window（ 注意定时器里面的this指向window）
        console.log(this);
        function fn() {
            console.log(this);
        }
        window.fn();
        window.setTimeout(function() {
            console.log(this);
        }, 1000);
        // 2. 方法调用中谁调用this指向谁
        var o = {
            sayHi: function() {
                console.log(this); // this指向的是 o 这个对象
            }
        }
        o.sayHi();
        var btn = document.querySelector('button');
        btn.addEventListener('click', function() {
                console.log(this); // 事件处理函数中的this指向的是btn这个按钮对象
            })
        // 3. 构造函数中this指向构造函数的实例
        function Fun() {
            console.log(this); // this 指向的是fun 实例对象
        }
        var fun = new Fun();
    </script>
```



### 1.2.7. location对象

#### 什么是 location 对象

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134223.png)

#### URL

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134245.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134269.png)

#### location 对象的属性

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134293.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134314.png)

#### 案例：5分钟自动跳转页面

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134337.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134361.png)

跳转页面用location就可以了

```js
	<body>
		<button>点击</button>
		<div></div>
		<script>
			var time = 5;
			var btn = document.querySelector('button');
			var div = document.querySelector('div');
			// 点击跳转
			btn.addEventListener('click', function () {
				// location.href='http://www.itcast.cn';
				setInterval(function () {
					if (time == 0) {
						location.href = 'http://www.baidu.cn';
					} else {
						div.innerHTML += '你将在' + time + '秒后跳转到链接'+'<br>';
						time--;
					}
				}, 1000);
			});
		</script>
	</body>
```

#### 案例：获取URL参数

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134382.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134405.png)
>login

```html
	<body>
		登录页面
		<form action="index.html">
			用户名:
			<input type="text" name="uname" />
			<input type="submit" value="提交" id="submit" />
		</form>
		<script>
			var btn = document.getElementById('submit');
			btn.addEventListener('click', function () {
				location.href = 'index.html';
			});
		</script>
	</body>
```

> index

```html
    <div></div>
	<script>
        console.log(location.search); // ?uname=andy
        // 1.先去掉？  substr('起始的位置'，截取几个字符);
        var params = location.search.substr(1); // uname=andy
        console.log(params);
        // 2. 利用=把字符串分割为数组 split('=');
        var arr = params.split('=');
        console.log(arr); // ["uname", "ANDY"]
        var div = document.querySelector('div');
        // 3.把数据写入div中
        div.innerHTML = arr[1] + '欢迎您';
    </script>
```

#### location对象的常见方法

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134430.png)

href和assign和replace都可以跳转网页,但是assign可以记录历史,所以可以后退页面
reload重新加载页面,如果为空,或者事false,强制刷新时true,因为系统本地是有缓存的

```js
    <button>点击</button>
    <script>
        var btn = document.querySelector('button');
        btn.addEventListener('click', function() {
            // 记录浏览历史，所以可以实现后退功能
            // location.assign('http://www.itcast.cn');
            // 不记录浏览历史，所以不可以实现后退功能
            // location.replace('http://www.itcast.cn');
            location.reload(true);
        })
    </script>
```

### 1.2.8. navigator对象

​	navigator 对象包含有关浏览器的信息，它有很多属性，我们最常用的是 userAgent，该属性可以返回由客户机发送服务器的 user-agent 头部的值。

下面前端代码可以判断用户那个终端打开页面，实现跳转

```js
if((navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i))) {
    window.location.href = "";     //手机
 } else {
    window.location.href = "";     //电脑
 }
```

### 1.2.9 history对象

​	window对象给我们提供了一个 history对象，与浏览器历史记录进行交互。该对象包含用户（在浏览器窗口中）访问过的URL
==这个是方法,所以要加括号==

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134454.png)

history对象一般在实际开发中比较少用，但是会在一些 OA 办公系统中见到。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134474.png)

## 1.3. JS执行机制

以下代码执行的结果是什么？

```js
 console.log(1);
 
 setTimeout(function () {
     console.log(3);
 }, 1000);
 
 console.log(2);
```

以下代码执行的结果是什么？

```js
 console.log(1);
 
 setTimeout(function () {
     console.log(3);
 }, 0);
 
 console.log(2);
```



### 1.3.1 JS 是单线程

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134497.png)

```js
	单线程就意味着，所有任务需要排队，前一个任务结束，才会执行后一个任务。如果前一个任务耗时很长，后一个任务就不得不一直等着。
	这样所导致的问题是： 如果 JS 执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。
```

### 1.3.2 同步任务和异步任务

​	单线程导致的问题就是后面的任务等待前面任务完成，如果前面任务很耗时（比如读取网络数据），后面任务不得不一直等待！！

​	为了解决这个问题，利用多核 CPU 的计算能力，HTML5 提出 Web Worker 标准，允许 JavaScript 脚本创建多个线程，但是子线程完全受主线程控制。于是，JS 中出现了**同步任务**和**异步任务**。

#### 同步

​	前一个任务结束后再执行后一个任务，程序的执行顺序与任务的排列顺序是一致的、同步的。比如做饭的同步做法：我们要烧水煮饭，等水开了（10分钟之后），再去切菜，炒菜。

#### 异步

​	你在做一件事情时，因为这件事情会花费很长时间，在做这件事的同时，你还可以去处理其他事情。比如做饭的异步做法，我们在烧水的同时，利用这10分钟，去切菜，炒菜。

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134521.png)

> ```js
> JS中所有任务可以分成两种，一种是同步任务（synchronous），另一种是异步任务（asynchronous）。
> 
> 同步任务指的是：
> 	在主线程上排队执行的任务，只有前一个任务执行完毕，才能执行后一个任务；
> 异步任务指的是：
> 	不进入主线程、而进入”任务队列”的任务，当主线程中的任务运行完了，才会从”任务队列”取出异步任务放入主线程执行。
> ```

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134544.png)

### 1.3.3 JS执行机制（事件循环）

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134569.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134594.png)

![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151134618.png)

### 1.3.4 代码思考题

```js
 console.log(1);
 document.onclick = function() {
   console.log('click');
 }

 setTimeout(function() {
   console.log(3)
 }, 3000)
 console.log(2);
```



#  **day05 - Web APIs**

> **学习目标:**
>
> 能够说出常见 offset 系列属性的作用
>
> 能够说出常见 client 系列属性的作用
>
> 能够说出常见 scroll 系列属性的作用
>
> 能够封装简单动画函数

## 1.1. 元素偏移量 offset 系列

### 1.1.1 offset 概述 

offset 翻译过来就是偏移量， 我们使用 offset系列相关属性可以动态的得到该元素的位置（偏移）、大小等。

1. 获得元素距离带有定位父元素的位置

2. 获得元素自身的大小（宽度高度）

3. 注意：返回的数值都不带单位

   

   offset对于一些没有父级元素或者有父级元素但是父级元素没有定位的标签来说它们返回的是相对于body的值

   ![](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135349.png)



### 1.1.2 offset 与 style 区别 

#### offset

- offset 可以得到任意样式表中的样式值，**包括自定义的样式表**

- offset 系列获得的数值是没有单位的

- offsetWidth 包含padding+border+width，**这些值是加在一起的，不是分开书写**

- offsetWidth 等属性是只读属性，只能获取不能赋值

- > 所以，我们想要获取元素大小位置，用offset更合适

#### style

- style 只能得到行内样式表中的样式值，**你自己自定义的css样式表是无法得到的，只能输出行内样式表**

- style.width 获得的是带有单位的字符串

- style.width 获得不包含padding和border 的值

- style.width 是可读写属性，可以获取也可以赋值

- > 所以，我们想要给元素更改值，则需要用style改变

> **因为平时我们都是给元素注册触摸事件，所以重点记住 targetTocuhes**

### 1.1.3  案例：获取鼠标在盒子内的坐标

1. 我们在盒子内点击，想要得到鼠标距离盒子左右的距离。
2. 首先得到鼠标在页面中的坐标（e.pageX, e.pageY）
3. 其次得到盒子在页面中的距离 ( box.offsetLeft, box.offsetTop)
4. 用鼠标距离页面的坐标减去盒子在页面中的距离，得到 鼠标在盒子内的坐标
5. 如果想要移动一下鼠标，就要获取最新的坐标，使用鼠标移动

```javascript
var box = document.querySelector('.box');
box.addEventListener('mousemove', function(e) {
var x = e.pageX - this.offsetLeft;
var y = e.pageY - this.offsetTop;
this.innerHTML = 'x坐标是' + x + ' y坐标是' + y;
})
```

### 1.1.4  案例：模态框拖拽

弹出框，我们也称为模态框。

​	1.点击弹出层，会弹出模态框， 并且显示灰色半透明的遮挡层。

​	2.点击关闭按钮，可以关闭模态框，并且同时关闭灰色半透明遮挡层。

​	3.鼠标放到模态框最上面一行，可以按住鼠标拖拽模态框在页面中移动。

​	4.鼠标松开，可以停止拖动模态框移动

### 1.1.5. 案例分析:

1. 点击弹出层， 模态框和遮挡层就会显示出来 display:block;
2. 点击关闭按钮，模态框和遮挡层就会隐藏起来 display:none;
3. 在页面中拖拽的原理：鼠标按下并且移动， 之后松开鼠标
4. 触发事件是鼠标按下mousedown，鼠标移动mousemove 鼠标松开 mouseup
5. 拖拽过程:  鼠标移动过程中，获得最新的值赋值给模态框的left和top值，这样模态框可以跟着鼠标走了
6. 鼠标按下触发的事件源是最上面一行，就是  id 为 title 
7. 鼠标的坐标减去 鼠标在盒子内的坐标， 才是模态框真正的位置。
8. 鼠标按下，我们要得到鼠标在盒子的坐标。
9. 鼠标移动，就让模态框的坐标  设置为  ：鼠标坐标 减去盒子坐标即可，注意移动事件写到按下事件里面。
10. 鼠标松开，就停止拖拽，就是可以让鼠标移动事件解除  

```javascript
 // 1. 获取元素
        var login = document.querySelector('.login');
        var mask = document.querySelector('.login-bg');
        var link = document.querySelector('#link');
        var closeBtn = document.querySelector('#closeBtn');
        var title = document.querySelector('#title');
        // 2. 点击弹出层这个链接 link  让mask 和login 显示出来
        link.addEventListener('click', function() {
                mask.style.display = 'block';
                login.style.display = 'block';
            })
            // 3. 点击 closeBtn 就隐藏 mask 和 login 
        closeBtn.addEventListener('click', function() {
                mask.style.display = 'none';
                login.style.display = 'none';
            })
            // 4. 开始拖拽
            // (1) 当我们鼠标按下， 就获得鼠标在盒子内的坐标
        title.addEventListener('mousedown', function(e) {
            var x = e.pageX - login.offsetLeft;
            var y = e.pageY - login.offsetTop;
            // (2) 鼠标移动的时候，把鼠标在页面中的坐标，减去 鼠标在盒子内的坐标就是模态框的left和top值
            document.addEventListener('mousemove', move)

            function move(e) {
                login.style.left = e.pageX - x + 'px';
                login.style.top = e.pageY - y + 'px';
            }
            // (3) 鼠标弹起，就让鼠标移动事件移除
            document.addEventListener('mouseup', function() {
                document.removeEventListener('mousemove', move);
            })
        })

```

> 完整代码

```html
<!DOCTYPE html>
<html>

<head lang="en">
    <meta charset="UTF-8">
    <title></title>
    <style>
        .login-header {
            width: 100%;
            text-align: center;
            height: 30px;
            font-size: 24px;
            line-height: 30px;
        }
        
        ul,
        li,
        ol,
        dl,
        dt,
        dd,
        div,
        p,
        span,
        h1,
        h2,
        h3,
        h4,
        h5,
        h6,
        a {
            padding: 0px;
            margin: 0px;
        }
        
        .login {
            display: none;
            width: 512px;
            height: 280px;
            position: fixed;
            border: #ebebeb solid 1px;
            left: 50%;
            top: 50%;
            background: #ffffff;
            box-shadow: 0px 0px 20px #ddd;
            z-index: 9999;
            transform: translate(-50%, -50%);
        }
        
        .login-title {
            width: 100%;
            margin: 10px 0px 0px 0px;
            text-align: center;
            line-height: 40px;
            height: 40px;
            font-size: 18px;
            position: relative;
            cursor: move;
        }
        
        .login-input-content {
            margin-top: 20px;
        }
        
        .login-button {
            width: 50%;
            margin: 30px auto 0px auto;
            line-height: 40px;
            font-size: 14px;
            border: #ebebeb 1px solid;
            text-align: center;
        }
        
        .login-bg {
            display: none;
            width: 100%;
            height: 100%;
            position: fixed;
            top: 0px;
            left: 0px;
            background: rgba(0, 0, 0, .3);
        }
        
        a {
            text-decoration: none;
            color: #000000;
        }
        
        .login-button a {
            display: block;
        }
        
        .login-input input.list-input {
            float: left;
            line-height: 35px;
            height: 35px;
            width: 350px;
            border: #ebebeb 1px solid;
            text-indent: 5px;
        }
        
        .login-input {
            overflow: hidden;
            margin: 0px 0px 20px 0px;
        }
        
        .login-input label {
            float: left;
            width: 90px;
            padding-right: 10px;
            text-align: right;
            line-height: 35px;
            height: 35px;
            font-size: 14px;
        }
        
        .login-title span {
            position: absolute;
            font-size: 12px;
            right: -20px;
            top: -30px;
            background: #ffffff;
            border: #ebebeb solid 1px;
            width: 40px;
            height: 40px;
            border-radius: 20px;
        }
    </style>
</head>

<body>
    <div class="login-header"><a id="link" href="javascript:;">点击，弹出登录框</a></div>

    <div id="login" class="login">

        <div id="title" class="login-title">登录会员
            <span><a id="closeBtn" href="javascript:void(0);" class="close-login">关闭</a></span>
        </div>
        
        <div class="login-input-content">
            <div class="login-input">
                <label>用户名：</label>
                <input type="text" placeholder="请输入用户名" name="info[username]" id="username" class="list-input">
            </div>
            <div class="login-input">
                <label>登录密码：</label>
                <input type="password" placeholder="请输入登录密码" name="info[password]" id="password" class="list-input">
            </div>
        </div>
        <div id="loginBtn" class="login-button"><a href="javascript:void(0);" id="login-button-submit">登录会员</a></div>
    </div>
    <!-- 遮盖层 -->
    <div id="bg" class="login-bg"></div>
    <script>
        // 1. 获取元素
        var login = document.querySelector('.login');
        var mask = document.querySelector('.login-bg');
        var link = document.querySelector('#link');
        var closeBtn = document.querySelector('#closeBtn');
        var title = document.querySelector('#title');
        // 2. 点击弹出层这个链接 link  让mask 和login 显示出来
        link.addEventListener('click', function() {
                mask.style.display = 'block';
                login.style.display = 'block';
            })
            // 3. 点击 closeBtn 就隐藏 mask 和 login 
        closeBtn.addEventListener('click', function() {
                mask.style.display = 'none';
                login.style.display = 'none';
            })
            // 4. 开始拖拽
            // (1) 当我们鼠标按下， 就获得鼠标在盒子内的坐标
        title.addEventListener('mousedown', function(e) {
            var x = e.pageX - login.offsetLeft;
            var y = e.pageY - login.offsetTop;
            // (2) 鼠标移动的时候，把鼠标在页面中的坐标，减去 鼠标在盒子内的坐标就是模态框的left和top值
            document.addEventListener('mousemove', move)

            function move(e) {
                login.style.left = e.pageX - x + 'px';
                login.style.top = e.pageY - y + 'px';
            }
            // (3) 鼠标弹起，就让鼠标移动事件移除
            document.addEventListener('mouseup', function() {
                document.removeEventListener('mousemove', move);
            })
        })
    </script>
</body>

</html>
```



### 1.1.6  案例：仿京东放大镜

1. 整个案例可以分为三个功能模块
2. 鼠标经过小图片盒子， 黄色的遮挡层 和 大图片盒子显示，离开隐藏2个盒子功能
3. 黄色的遮挡层跟随鼠标功能。 
4. 移动黄色遮挡层，大图片跟随移动功能。

### 1.1.7. 案例分析:

1. 黄色的遮挡层跟随鼠标功能。
2. 把鼠标坐标给遮挡层不合适。因为遮挡层坐标以父盒子为准。
3. 首先是获得鼠标在盒子的坐标。 
4. 之后把数值给遮挡层做为left 和top值。
5. 此时用到鼠标移动事件，但是还是在小图片盒子内移动。
6. 发现，遮挡层位置不对，需要再减去盒子自身高度和宽度的一半。
7. 遮挡层不能超出小图片盒子范围。
8. 如果小于零，就把坐标设置为0
9. 如果大于遮挡层最大的移动距离，就把坐标设置为最大的移动距离
10. 遮挡层的最大移动距离：小图片盒子宽度 减去 遮挡层盒子宽度





```javascript
window.addEventListener('load', function() {
    var preview_img = document.querySelector('.preview_img');
    var mask = document.querySelector('.mask');
    var big = document.querySelector('.big');
    // 1. 当我们鼠标经过 preview_img 就显示和隐藏 mask 遮挡层 和 big 大盒子
    preview_img.addEventListener('mouseover', function() {
        mask.style.display = 'block';
        big.style.display = 'block';
    })
    preview_img.addEventListener('mouseout', function() {
            mask.style.display = 'none';
            big.style.display = 'none';
        })
        // 2. 鼠标移动的时候，让黄色的盒子跟着鼠标来走
    preview_img.addEventListener('mousemove', function(e) {
        // (1). 先计算出鼠标在盒子内的坐标
        var x = e.pageX - this.offsetLeft;
        var y = e.pageY - this.offsetTop;
        // console.log(x, y);
        // (2) 减去盒子高度 300的一半 是 150 就是我们mask 的最终 left 和top值了
        // (3) 我们mask 移动的距离
        var maskX = x - mask.offsetWidth / 2;
        var maskY = y - mask.offsetHeight / 2;
        // (4) 如果x 坐标小于了0 就让他停在0 的位置
        // 遮挡层的最大移动距离
        var maskMax = preview_img.offsetWidth - mask.offsetWidth;
        if (maskX <= 0) {
            maskX = 0;
        } else if (maskX >= maskMax) {
            maskX = maskMax;
        }
        if (maskY <= 0) {
            maskY = 0;
        } else if (maskY >= maskMax) {
            maskY = maskMax;
        }
        mask.style.left = maskX + 'px';
        mask.style.top = maskY + 'px';
        // 3. 大图片的移动距离 = 遮挡层移动距离 * 大图片最大移动距离 / 遮挡层的最大移动距离
        // 大图
        var bigIMg = document.querySelector('.bigImg');
        // 大图片最大移动距离
        var bigMax = bigIMg.offsetWidth - big.offsetWidth;
        // 大图片的移动距离 X Y
        var bigX = maskX * bigMax / maskMax;
        var bigY = maskY * bigMax / maskMax;
        bigIMg.style.left = -bigX + 'px';
        bigIMg.style.top = -bigY + 'px';

    })

})
```

## 1.2. 元素可视区 client 系列

### 1.2.1 client概述

client 翻译过来就是客户端，我们使用 client 系列的相关属性来获取元素可视区的相关信息。通过 client
系列的相关属性可以动态的得到该元素的边框大小、元素大小等。

![图片3](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135371.png)

![图片4](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135399.png)

### 1.2.2. 淘宝 flexible.js 源码分析

立即执行函数 (function(){})()  或者 (function(){}())

主要作用： 创建一个独立的作用域。 避免了命名冲突问题

下面三种情况都会刷新页面都会触发 load 事件。  //**load 事件是页面窗口加载完毕了没有，windows.load()这个是一个大的函数**

1.a标签的超链接

2.F5或者刷新按钮（强制刷新）

3.前进后退按钮

但是 火狐中，有个特点，有个“往返缓存”，这个缓存中不仅保存着页面数据，还保存了DOM和JavaScript的状态；实际上是将整个页面都保存在了内存里。

所以此时后退按钮不能刷新页面。

此时可以使用 pageshow事件来触发。，这个事件在页面显示时触发，无论页面是否来自缓存。在重新加载页面中，pageshow会在load事件触发后触发；根据事件对象中的persisted来判断是否是缓存中的页面触发的pageshow事件

`注意这个事件给window添加。`



## 1.3.元素滚动 scroll 系列

### 1.3.1. scroll 概述

scroll 翻译过来就是滚动的，我们使用 scroll 系列的相关属性可以动态的得到该元素的大小、滚动距离等。

![图片5](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135418.png)

![图片6](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135437.png)

### 1.3.2. 页面被卷去的头部

如果浏览器的高（或宽）度不足以显示整个页面时，会自动出现滚动条。当滚动条向下滚动时，页面上面被隐藏掉的高度，我们就称为页面被卷去的头部。滚动条在滚动时会触发 onscroll事件。



### 1.3.3.案例：仿淘宝固定右侧侧边栏

1. 原先侧边栏是绝对定位
2. 当页面滚动到一定位置，侧边栏改为固定定位
3. 页面继续滚动，会让 返回顶部显示出来

### 1.3.4.案例分析: 

1. 需要用到页面滚动事件 scroll  因为是页面滚动，所以事件源是document
2. 滚动到某个位置，就是判断页面被卷去的上部值。
3. 页面被卷去的头部：可以通过window.pageYOffset 获得  如果是被卷去的左侧window.pageXOffset
4. 注意，元素被卷去的头部是element.scrollTop  , 如果是页面被卷去的头部 则是 window.pageYOffset
5. 其实这个值 可以通过盒子的 offsetTop可以得到，如果大于等于这个值，就可以让盒子固定定位了

**疑难点解答**
> 三个区域,第一个区域的高度为170px,当滚动的值大于170的时候,边缘的那个是固定的位置,相对于当前页面的位置的固定,此时继续滚动,这个边缘区域它的位置相对于页面来说是变化的,但是相对于我们的视觉是不动的

> 绝对定位的时候,为了让它能够跟着滚动条移动,此时让它距离页面的顶端总是保持300px的距离,这个时候被称为绝对定位

```javascript
  //1. 获取元素
        var sliderbar = document.querySelector('.slider-bar');
        var banner = document.querySelector('.banner');
        // banner.offestTop 就是被卷去头部的大小 一定要写到滚动的外面
        var bannerTop = banner.offsetTop
            // 当我们侧边栏固定定位之后应该变化的数值
        var sliderbarTop = sliderbar.offsetTop - bannerTop;
        // 获取main 主体元素
        var main = document.querySelector('.main');
        var goBack = document.querySelector('.goBack');
        var mainTop = main.offsetTop;
        // 2. 页面滚动事件 scroll
        document.addEventListener('scroll', function() {
            // console.log(11);
            // window.pageYOffset 页面被卷去的头部
            // console.log(window.pageYOffset);
            // 3 .当我们页面被卷去的头部大于等于了 172 此时 侧边栏就要改为固定定位
            if (window.pageYOffset >= bannerTop) {
                sliderbar.style.position = 'fixed';
                sliderbar.style.top = sliderbarTop + 'px';
            } else {
                sliderbar.style.position = 'absolute';
                sliderbar.style.top = '300px';
            }
            // 4. 当我们页面滚动到main盒子，就显示 goback模块
            if (window.pageYOffset >= mainTop) {
                goBack.style.display = 'block';
            } else {
                goBack.style.display = 'none';
            }

        })
```

### 1.3.5.页面被卷去的头部兼容性解决方案

需要注意的是，页面被卷去的头部，有兼容性问题，因此被卷去的头部通常有如下几种写法：

1. 声明了 DTD，使用 document.documentElement.scrollTop
2. 未声明 DTD，使用  document.body.scrollTop
3. 新方法 window.pageYOffset和 window.pageXOffset，IE9 开始支持

```javascript
function getScroll() {
    return {
      left: window.pageXOffset || document.documentElement.scrollLeft || document.body.scrollLeft||0,
      top: window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop || 0
    };
 } 
使用的时候  getScroll().left

```

## 1.4. 三大系列总结

![图片7](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202301151135457.png)

他们主要用法：

1.offset系列 经常用于获得元素位置    offsetLeft  offsetTop

2.client经常用于获取元素大小  clientWidth clientHeight

3.scroll 经常用于获取滚动距离 scrollTop  scrollLeft  

4.注意页面滚动的距离通过 window.pageXOffset  获得

## 1.5. mouseenter 和mouseover的区别

- 当鼠标移动到元素上时就会触发mouseenter 事件
- 类似 mouseover，它们两者之间的差别是
- mouseover 鼠标经过自身盒子会触发，经过子盒子还会触发。mouseenter  只会经过自身盒子触发
- 之所以这样，就是因为mouseenter不会冒泡
- 跟mouseenter搭配鼠标离开 mouseleave  同样不会冒泡


## 1.6. 动画函数封装

### 1.6.1. 动画实现原理 

> 核心原理：通过定时器 setInterval() 不断移动盒子位置。

实现步骤：

1. 获得盒子当前位置
2. 让盒子在当前位置加上1个移动距离
3. 利用定时器不断重复这个操作
4. 加一个结束定时器的条件
5. 注意此元素需要添加定位，才能使用element.style.left

### 1.6.2. 动画函数给不同元素记录不同定时器 

如果多个元素都使用这个动画函数，每次都要var 声明定时器。我们可以给不同的元素使用不同的定时器（自己专门用自己的定时器）。

> 核心原理：利用 JS 是一门动态语言，可以很方便的给当前对象添加属性。

```javascript
 function animate(obj, target) {
            // 当我们不断的点击按钮，这个元素的速度会越来越快，因为开启了太多的定时器
            // 解决方案就是 让我们元素只有一个定时器执行
            // 先清除以前的定时器，只保留当前的一个定时器执行
            clearInterval(obj.timer);
            obj.timer = setInterval(function() {
                if (obj.offsetLeft >= target) {
                    // 停止动画 本质是停止定时器
                    clearInterval(obj.timer);
                }
                obj.style.left = obj.offsetLeft + 1 + 'px';

            }, 30);
        }

```











