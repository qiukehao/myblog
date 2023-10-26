---
{"dg-publish":true,"permalink":"/02java//02java-web/03-java-script/","dgPassFrontmatter":true}
---

## JavaScript 的引入方式

内部脚本：将 JS 代码定义在 HTML 页面中
	JavaScript 代码必须位于\<script>\</script>标签之间
	在 HTML 文档中，可以在任意地方，放置任意数量的\<script>
	一般会把脚本置于\<body>元素的底部，可改善显示速度
```js
    <script>
        alert("hello world")
    </script>
```

外部脚本：将 JS 代码定义在外部 JS 文件中，然后引入到 HTML 页面中
	外部 JS 文件中，只包含 JS 代码，不包含\<script>标签
	\<script>标签不能自闭合
```html
<script src="../JS/demo.js"></script>
```

```js
alert("hello world")
```

## JS 的基础语法
区分大小写：与 Java 一样，变量名、函数名以及其他一切东西都是区分大小写的
每行结尾的分号可有可无
注释：
单行注释：// 注释内容
多行注释：/* 注释内容 \*/
大括号表示代码块
### 输出语法
使用 window.Alert () 写入警告框
使用 document.Write () 写入 HTML 输出 ,会将这个文字给写在第一行里面.
使用 console.Log () 写入浏览器控制台

### 变量
JavaScript 中用 var 关键字（variable 的缩写）来声明变量。
JavaScript 是一门弱类型语言，变量可以存放不同类型的值。
变量名需要遵循如下规则：
组成字符可以是任何字母、数字、下划线（）或美元符号（$）
数字不能开头
建议使用驼峰命名
var 定义的变量是全局变量, 并且变量可以重复定义, 这一点和这个 java 的语法不太一样
```js
var a = 3;
var a = '张三';  //后面定义的这个变量会把前面的这个变量给取消掉
alert(a);
```
ECMAScript 6 新增了 let 关键字来定义变量。它的用法类似于 var，但是所声明的变量，只在 let 关键字所在的代码块内有效，且不允许重复声明。
ECMAScript 6 新增了 const 关键字，用来声明一个只读的常量。一旦声明，常量的值就不能改变。
### 数据类型
**JavaScript 中分为：原始类型和引用类型。**
 number：数字（整数、小数、NaN(Not a Number)）, 只要是数字那么都是 number 类型
 string：字符串，单双引皆可, 带有引号的, 无论但单双引号都是字符串
 boolean：布尔。true，false
 null：对象为空返回的是一个 object 类型, 这是 js 创建的时候出现的错误, 延用至今
 undefined：当声明的变量未初始化时，该变量的默认值是 undefined
**使用 typeof 运算符可以获取数据类型：**
```js
var b = null;
console.log(typeof(b));//返回的值是object
```
### 运算符
 算术运算符：+ , - , * , / , % , ++ , --
 赋值运算符：= , += , -= , \*= , /= , %=
 比较运算符：> , < , >= , <= , != , == , === 
 逻辑运算符：&& , || , !
 三元运算符：条件表达式 ? True_value: false_value
 == 会进行类型转换，=== 不会进行类型转换
```js
var a = 10;
var b = "10";
console.log(a == b);  //true  ==会进行转化,number和String类型转换
console.log(a==10);  //true
console.log(a===b);  //false  这个不会进行转化
```

字符串类型转为数字：
将字符串字面值转为数字。如果字面值不是数字，则转为 NaN。
利用 `console.log(parseInt('123'));` 这个 parseInt 来进行转化
其他类型转为 boolean：(作为 if 语句的判断符的时候会用到这种转换)
Number：0 和 NaN为false，其他均转为true。
String：空字符串为false，其他均转为true。
Null 和 undefined ：均转为 false。

### 流程控制语句
和 java 语法的一样的, 不在介绍

### 函数
函数（方法）是被设计为执行特定任务的代码块。
JavaScript 函数通过 function 关键字进行定义，语法为：
**注意：**
形式参数不需要类型。因为 JavaScript 是弱类型语言
形式参数的数量和传递参数的数量可以不一致, 比如说形式参数是两个, 但是传递参数是四个, 这种情况下, 我们只接受前面那两个数据
返回值也不需要定义类型，可以在函数内部直接使用 return 返回即可
**定义方式 1**
```js
function add(a,b){
    return a+b;
}
console.log(add(1,2));
```
**定义方式 2**
```java
格式是:
var 加函数名字 = function(a,b){
	函数体
}
var add1 = function (a,b){
    return a+b;
}
console.log(add1(1,2));
```

## JS 对象
我们需要了解的是五种对象
Array String JSON BOM DOM 类对象
### 数组 Array 对象
#### 定义方式
有两种定义的方式
第一种: `var arr = new Array (1,2,3,4,5);`
第二种: `var arr = [1,2,3,4,5];`

```java
var arr = new Array(1,2,3,4,5);
for(array in arr){
    console.log(array);
}
```

JS 中的数组类似于 java 的集合, 长度是可变的, 类型是可变的.
```js
var arr = new Array(1,2,3,4,5);
arr[10]=10;
arr[8]='A';
arr[7]=true;
console.log(arr[10]);
```

#### 遍历数组
```js
//可以遍历出所有的元素
for(var i=0;i<arr.length;i++){
    console.log(arr[i]);
} 
//只能遍历出有值的元素,undefined元素遍历不出来
for(array in arr){
    console.log(array);
}
arr.forEach(function(e)) {
    console.log(element);
});
//箭头函数,简化函数的定义
arr.forEach(element => {
    console.log(element);
});
```

#### 添加元素和删除元素
push()	将新元素添加到数组的末尾，并返回新的长度。
splice()	从数组中删除元素。
```js
arr.push(100);
arr.forEach(element => {
    console.log(element);
});
arr.splice(100);
arr.forEach(element => {
    console.log(element);
});
```

### 字符串 String
#### 定义方式
第一种: `var 变量名 = new String("…") ;`
第二种: `var 变量名 = "…" ;`
#### 常用方法

| 方法          | 描述                   |
|-------------|----------------------|
| charAt()    | 返回在指定位置的字符。          |
| indexOf()   | 检索字符串。               |
| trim()      | 去除字符串两边的空格           |
| substring() | 提取字符串中两个指定的索引号之间的字符。 |

### JSON 对象
#### js 对象
学习这个之前我们要首先了解这个 js 如何定义对象
js 通过 var 声明直接定义对象
```js
var 对象名 = {
属性名1: 属性值1, 
属性名2: 属性值2,
属性名3: 属性值3,
函数名称: function(形参列表){}
};

```

调用这些对象的内部属性的时候使用下面的方式
```js
对象名.属性名; person.name;
对象名.函数名; person.eat();
```

举例
```js
var Student= {
    name : "张三",
    age : 18,
    eat : function(){
        console.log("eat");
    }
}
console.log(Student.name);
console.log(Student.age);
Student.eat();
```

#### JSON 对象介绍
概念：JavaScript Object Notation，JavaScript 对象标记法。
JSON 是通过 JavaScript 对象标记法书写的文本。
由于其语法简单, 层次结构鲜明, 先多用于作为数据载体, 在网络中进行数据传输
**json 格式**, 每个键值对都是具有双引号包裹的
```json
{
    "name":"Tom",
    "age":20,
    "gender":"male"
}

```
#### JSON 的基础语法介绍
数字（整数或浮点数, 直接书写）
字符串（用双引号包裹）
逻辑值（true 或 false, 直接书写）
数组（用方括号包裹）
对象（用花括号包裹）
null
```js
//定义json对象
var  jsonTest = '{"name" : "张三","age":  16,"arr": [1,2,3,4,5],"boo": true}'
console.log(jsonTest.name); //输出undefine
var obj = JSON.parse(jsonTest);
console.log(obj.name);//输出张三
var jsonTest1 = JSON.stringify(obj);
console.log(jsonTest1);
```

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310071612846.png)

### BOM 对象
概念：Browser Object Model  浏览器对象模型，允许 JavaScript 与浏览器对话， JavaScript 将浏览器的各个组成部分封装为对象。
**组成：**
	Window：浏览器窗口对象
	Navigator：浏览器对象
	Screen：屏幕对象
	History：历史记录对象
	Location：地址栏对象
作为后端开发人员我们只需要了解这个 window 和 location 就行了
#### Window
直接使用window，其中 window. 可以省略。
方法
 alert()：显示带有一段消息和一个确认按钮的警告框。
 confirm()：显示带有一段消息以及确认按钮和取消按钮的对话框。
 setInterval()：按照指定的周期（以毫秒计）来调用函数或计算表达式。
 setTimeout()：在指定的毫秒数后调用函数或计算表达式。
```js
window.alert("hello BOM window");
var flag = window.confirm("你确定要删除吗");  //这个为了确定这个你的选择,所以这个函数是有返回值的,当你选择确认的时候,返回true,当你取消的时候返回false
if(flag){
    alert("确定删除");
}else {
    alert("取消删除");
}
var a = 0;
window.setInterval(function(){
    console.log("执行了多少次"+(++a));
},2000);
```

#### Location
介绍：地址栏对象。
获取：使用 window. Location 获取，其中 window. 可以省略。
属性：
Href：设置或返回完整的 URL。
```js
alert(location.href);  //获取当前地址栏地址

location.href="http://www.baidu.com"; //将地址栏地址设置成你设置的地址
```

### DOM 
#### DOM 的作用
概念：Document Object Model ，文档对象模型。
**将标记语言的各个组成部分封装为对应的对象：**
	Document：整个文档对象
	Element：元素对象
	Attribute：属性对象
	Text：文本对象
	Comment：注释对象
 **JavaScript 通过 DOM，就能够对 HTML 进行操作：**
	1. 改变 HTML 元素的内容
	2. 改变 HTML 元素的样式（CSS）
	3. 对 HTML DOM 事件作出反应
	4. 添加和删除 HTML 元素
#### DOM 种类
Core DOM - 所有文档类型的标准模型
	1. Document：整个文档对象
	2. Element：元素对象
	3. Attribute：属性对象
	4. Text：文本对象
	5. Comment：注释对象
XML DOM - XML 文档的标准模型  
HTML DOM - HTML 文档的标准模型
	1. Image：\<img>
	2. Button ：\<input type='button'>

我们主要获取的是 DOM-HTML

#### 获取 DOM 属性值

当你获取这个元素的 DOM 对象之后，我们可以去 js 的参考文档中去查询你要修改的是什么属性
[参考文档](https://www.w3school.com.cn/jsref/index.asp)
```js
<script>
    //DOM获取元素
    //根据id值来获取 这个DOM对象
    var h1= document.getElementById("h1");
    h1.src="../images/on.gif";
    console.log(h1);
    //根据这个类名来获取对象
    var arr = document.getElementsByClassName("cls");
    console.log(arr);
    for(let i=0;i<arr.length;i++){
        const div = arr[i];
        div.innerHTML+="<font color='red'>VeryGood</font>";
    }
    //根据name来获取对象
    var hobbies = document.getElementsByName("hobby");
    console.log(hobbies);
    for(let i=0;i<hobbies.length;i++){
        let hobby1 = hobbies[i];
        hobby1.checked=true;
    }
</script>
```


## JS 事件

### 事件监听
事件：HTML 事件是发生在 HTML 元素上的 “事情”。比如：
	按钮被点击
	鼠标移动到元素上
	按下键盘按键
事件监听：JavaScript可以在事件被侦测到时 执行代码。

### 事件绑定
js 可以通过两种方法来绑定这个 DOM 对象
```js
//绑定事件对象,通过标签绑定
function myFunction(){
    //alert("hello");
    h1.src="../images/off.gif";
}
//通过DOM获取对象来进行更改
var light = document.getElementById("light");
light.onclick = function(){
    h1.src="../images/off.gif";
}
```

### JS 中常见的事件

| 事件名         | 说明           |
|-------------|--------------|
| onclick     | 鼠标单击事件       |
| onblur      |元素失去焦点 一般用于输入框|
| onfocus     |元素获得焦点 一般用于输入框|
| onload      |某个页面或图像被完成加载，可以通过刷新来查看|
| onsubmit    | 当表单提交时触发该事件  |
| onkeydown   |某个键盘的键被按下|
| onmouseover | 鼠标被移到某元素之上   |
| onmouseout  | 鼠标从某元素移开     |

### JS 案例
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310082240145.png)

要求
点击 “点亮”按钮点亮灯泡，点击“熄灭”按钮熄灭灯泡。
输入框鼠标聚焦后，展示小写；鼠标离焦后，展示大写。
点击 “全选”按钮使所有的复选框呈现被选中的状态，点击 “反选”按钮使所有的复选框呈现取消勾选的状态。
```html
<body>
    <img id="light" src="../images/off.gif"> <br>

    <input type="button" value="点亮" onclick="light()"> <input type="button"  value="熄灭" onclick="off()">

    <br> <br>

    <input type="text" id="name" value="ITCAST">
    <br> <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
    <br>

    <input type="button" value="全选" onclick="selectAll()" > 
    <input type="button" value="反选" onclick="notall()" >

    <script>
        var img = document.getElementById("light");
        function light() {
            img.src="../images/on.gif";
        }
        function off() {
            img.src="../images/off.gif";
        }
         
        var text = document.getElementById("name");
        text.onblur = function () {
            text.value = "itcast";
        }
        text.onfocus = function () {
            text.value = "ITCAST";
        }


        var check = document.getElementsByName("hobby");
        function selectAll() {
            for (let i = 0; i < check.length; i++) {
                check[i].checked =true;
            }
        }

        function notall() {
            for (let i = 0; i < check.length; i++) {
                check[i].checked =false;
            }
        }

    </script>
</body>
```

## VUE
Vue 是一套前端框架，免除原生 JavaScript 中的 DOM 操作，简化书写。
基于 MVVM (Model-View-ViewModel)思想，实现数据的**双向绑定**，将编程的关注点放在数据上
框架是一个半成品的软件，是一套可重用的，通用的，软件基础代码模型，基于框架进行开发，更加快捷，更加高效
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310082006096.png)

```html
</head>
<body>
    <div id="app">
        <input type="text" v-model="message">
        {{message}}  //这个message和input的message的内容是一样的,会进行同步修改
    </div>
</body>
    <script>
        new new Vue({
            el: "#app",
            data:{
                message:"hello world"
            }
        })
    </script>
</html>
```

### 常用指令
VUE 指令是指 HTML 标签上带有 **v-** 前缀的特殊属性，不同指令具有不同含义。例如：v-if，v-for…

| 指令        | 作用                             |
|-----------|--------------------------------|
| v-bind    | 为HTML标签绑定属性值，如设置 href , css样式等 |
| v-model   | 在表单元素上创建双向数据绑定                 |
| v-on      | 为HTML标签绑定事件                    |
| v-if      | 条件性的渲染某元素，判定为true时渲染,否则不渲染     |
| v-else-if |
| v-else    |
| v-show    | 根据条件展示某元素，区别在于切换的是display属性的值  |
| v-for     | 列表渲染，遍历容器的元素或者对象的属性            |


**vbind**
```html
    <script>
        new new Vue({
            el: "#app",
            data:{
                message:"hello world",
                url:"https://www.baidu.com"
            },
            methods:{
                handle: function(){
                    alert("hello world")
                }
            }
        })
    </script>
	    //利用这个v-bind可以将这个html中原有的标签绑定vue的元素
        <a v-bind:href = "url">超链接</a>
        <a :href = "url">超链接</a>
        <input type="text" v-model="url">
```

**von**
绑定事件
在这个 vue 中 methods 区域中绑定方法, 然后我们通过这个 v-on: 事件="方法名"; 来绑定vue
```js
<input type="button" value="点我一下" v-on:click="handle"></input>
    <script>
        new new Vue({
            el: "#app",
            data:{
                message:"hello world",
                url:"https://www.baidu.com"
            },
            methods:{
                handle: function(){
                    alert("hello world")
                }
            }
        })
    </script>
```

**vif elseif else  vshow**
这三个是连在一起用的,
```html
年龄<input type="text" v-model="age">经判定,为:
<span v-if="age <= 35">年轻人(35及以下)</span>
<span v-else-if="age > 35 && age < 60">中年人(35-60)</span>
<span v-else>老年人(60及以上)</span>
```

对于这个 vshow
```html
年龄<input type="text" v-model="age">经判定,为:
<span v-show="age <= 35">年轻人(35及以下)</span>
<span v-show="age > 35 && age < 60">中年人(35-60)</span>
<span v-show="age >= 60">老年人(60及以上)</span>
```
v-show 和 v-if 的作用效果是一样的，只是原理不一样
浏览器呈现的效果是一样的，但是浏览器中 html 源码不一样。v-if 指令，不满足条件的标签代码直接没了，而 v-show 指令中，不满足条件的代码依然存在，只是添加了 css 样式来控制标签不去显示。
**vfor**
```
<标签 v-for="变量名 in 集合模型数据">
    {{变量名}}
</标签>
```

需要注意的是：需要循环那个标签，v-for 指令就写在那个标签上。
有时我们遍历时需要使用索引，那么 v-for 指令遍历的语法格式如下：
```
<标签 v-for="(变量名,索引变量) in 集合模型数据">
    <!--索引变量是从0开始，所以要表示序号的话，需要手动的加1-->
   {{索引变量 + 1}} {{变量名}}
</标签>
```

```html
 <div id="app">
     <div v-for="addr in addrs">{{addr}}</div>
     <hr>
     <div v-for="(addr,index) in addrs">{{index + 1}} : {{addr}}</div>

<script>
    //定义Vue对象
    new Vue({
        el: "#app", //vue接管区域
        data:{
           addrs:["北京", "上海", "西安", "成都", "深圳"]
        },
        methods: {
            
        }
    })
</script>
```


### VUE 的生命周期
生命周期：指一个对象从创建到销毁的整个过程。
生命周期的八个阶段：每触发一个生命周期事件，会自动执行一个生命周期方法 (钩子)。

| 状态            | 阶段周期 |
|---------------|------|
| beforeCreate  | 创建前  |
| created       | 创建后  |
| beforeMount   | 挂载前  |
| mounted       | 挂载完成 |
| beforeUpdate  | 更新前  |
| updated       | 更新后  |
| beforeDestroy | 销毁前  |
| destroyed     | 销毁后  |
我们只需要了解这个 mountes 就行了
**mounted：挂载完成，Vue 初始化成功，HTML 页面渲染成功。（发送请求到服务端，加载数据）**


### 案例
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202310082241670.png)

```html
<body>
    <div id="app">
        <table border="1" cellspacing="0" width="60%">
            <tr>
                <th>编号</th>
                <th>姓名</th>
                <th>年龄</th>
                <th>性别</th>
                <th>成绩</th>
                <th>等级</th>
            </tr>
            <tr align="center" v-for="(user, index) in users">
                <td>{{index+1}}</td>
                <td>{{user.name}}</td>
                <td>{{user.age}}</td>
                <td><span v-if="user.gender==1">男</span> <span v-else>女</span></td>
                <td>{{user.score}}</td>
                <td>
                    <span v-if="user.score>=80">优秀</span>
                    <span v-else-if="user.score<80&&user.score>=60">及格</span>
                    <span style="color: red;" v-else>不及格</span>
                </td>
            </tr>
        </table>

    </div>
</body>
<script>
    new Vue({
        el:"#app",
        data:{
            users: [{
                name: "Tom",
                age: 20,
                gender: 1,
                score: 78
            },{
                name: "Rose",
                age: 18,
                gender: 2,
                score: 86
            },{
                name: "Jerry",
                age: 26,
                gender: 1,
                score: 90
            },{
                name: "Tony",
                age: 30,
                gender: 1,
                score: 52
            }]
        },
        methods: {
            
        },
    })
</script>
```