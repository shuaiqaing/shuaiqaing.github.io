---
layout: post
title:  "初学JavaScript教程"
date:   2014-5-3 9:10:16 +0800
categories: jekyll update
---
初次认识JavaScript
JavaScript 是 Web 的编程语言。

所有现代的 HTML 页面都使用 JavaScript。

JavaScript 非常容易学。
写的第一个JavaScript语言
&lt;script&gt;script&lt;/script&gt;
	alert('hello word!');
&lt;script&gt;script&lt;/script&gt;
以及简单事件
&lt;button type="button" onclick="alert('欢迎!')"&gt;点我!&lt;/button&gt;

JavaScript用法
HTML 中的脚本必须位于 &lt;script&gt; 与 &lt;/script&gt; 标签之间。脚本可被放置在 HTML 页面的 &lt;body&gt; 和 &lt;head&gt; 部分中。
如需在 HTML 页面中插入 JavaScript，请使用  &lt;script&gt; 标签。
&lt;script&gt; 和 &lt;/script&gt;  会告诉 JavaScript 在何处开始和结束。
&lt;script&gt; 和 &lt;/script&gt;  之间的代码行包含了 JavaScript
//简单来个示例
&lt;script&gt;<br>
alert("我的第一个 JavaScript");<br>
&lt;/script&gt;
如同我们刚看到的 弹出hello word！一样
接下来就说下事件
上面例子中的 JavaScript 语句，会在页面加载时执行。

通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。

如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。
先来个示例：
&lt;!DOCTYPE html&gt;<br>&lt;html&gt;<p>&lt;head&gt;<br><span class="marked">&lt;script&gt;<br>
function myFunction()<br>
{<br>
document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";<br>
}<br>
&lt;/script&gt;</span><br>
&lt;/head&gt;</p>
<p>&lt;body&gt;</p>
<p>&lt;h1&gt;我的 Web 页面&lt;/h1&gt;</p>
<p>&lt;p id="demo"&gt;一个段落&lt;/p&gt;</p>
<p>&lt;button type="button" <span class="marked">onclick="myFunction()"</span>&gt;尝试一下&lt;/button&gt;</p>
<p>&lt;/body&gt;<br>
&lt;/html&gt;
//这样当我们点击尝试一下 或触发事件 将id为demo的内容替换为 我们要输出的内容<br><br>

介绍到这里 如果上面直接实践的话 基本的操作就会明白点我们再介绍下他的基本语法<br>
数值类型：<br>
1.数值型：例如 3  5  1.2  3.4<br>
2.布尔：两个值真或假，如true或false <br>
3.字符串：例如: ‘I am a jelly doughnut’由一个或多个字符组成, 用单引号或双引号引起来的一系列的字符(也可以称之为一个字符串对象）<br>
4.空值：用关键字NULL表示．如果变量声明但是没有赋值就是这个类型<br>
5.未定义：用关键字undefined表示，如果变量未声明则就是未定义类型<br>
6.数组：用new Array()声明的就是数据(也可以称之为一个数组对象)<br>
7.对象：{}使用一对花括号声明的就是一个对象<br><br>

执行顺序：js代码自上而下执行，和php代码执行顺序一致<br>
区分大小写：js中的代码严格区分大小写<br>
结束符：没行结尾的分号可有可无<br><br>

JavaScript 变量JavaScript 使用关键字 var 来定义变量， 使用等号来为变量赋值：<br>
var x, length<br>

x = 5<br>

length = 6 <br>
变量可以通过变量名访问。在指令式语言中，变量通常是可变的。字面量是一个恒定的值。<br><br>

JavaScript 注释<br>
不是所有的 JavaScript 语句都是"命令"。双斜杠 // 后的内容将会被浏览器忽略：<br>
//我才不执行<br>
JavaScript 函数<br>
JavaScript 语句可以写在函数内，函数可以重复引用：<br>
引用一个函数 = 调用函数(执行函数内的语句)。<br><br>

function myFunction(a, b) {<br>
    return a * b;                                // 返回 a 乘于 b 的结果<br>
}<br>
JavaScript 对大小写敏感。<br>
JavaScript 对大小写是敏感的。<br>
当编写 JavaScript 语句时，请留意是否关闭大小写切换键。<br>
函数 getElementById 与 getElementbyID 是不同的。<br>
同样，变量 myVariable 与 MyVariable 也是不同的。<br>
语法 就先结束<br>
Javascript中的常用事件<br>
鼠标事件（onclick、onmouseover、onmouseout、onmousemove）<br>
键盘事件（onkeydown、onkeyup）<br>
表单事件（onblur、onsubmit、onchange）<br>
我们就先写两个示例：<br>
例如：鼠标移到p标签上的时候更改文字内容<br>
&lt;meta charset=utf-8&gt;<br>
&lt;a id='content' onmouseover='fun()' href='' onmouseout='fun2()'>请移动上来&lt;/a&gt;<br>
&lt;script&gt;<br>
function fun(){<br>
	document.getElementById("content").innerHTML='我被改变了'<br>
}<br>
function fun2(){<br>
	document.getElementById("content").innerHTML='请移动上来'<br>
}<br>
&lt;/script&gt;<br>
当鼠标经过图片的时候给出提示<br>
&lt;meta charset=utf-8&gt;<br>
&lt;img src='a.jpg' onmousemove='fun()'&gt;<br>
&lt;script&gt;<br>
function fun(){<br>
	alert("鼠标经过我啦！")<br>
}<br>
&lt;/script&gt;<br>
//有这么两个示例 就能简单了解下啦<br><br>

JavaScript中的内置对象<br>
javascript内置对象的定义和内置对象的分类<br><br>

Math对象的round、ceil、floor、random方法<br>
Math对象提供了大量的数学常量和数学函数，在使用Math对象的时候，不需要使用关键字new创建对象，而应直接使用：对象名.属性名、对象名.方法名()<br>
 Math.round()：四舍五入<br>
 例如：alert(Math.round(1.2))结果是1<br>
 Math.ceil()：向上取整<br>
 例如：alert(Math.round(1.2))结果是2<br>
 Math.floor()：向下取整<br>
 例如：alert(Math.round(1.2))结果是1<br>
 Math.random()：产生0---1之间的随机数<br>
 例如：alert(parseInt(Math.random()*10))则会产生一个1到10之间的随机数<br>
String对象的创建和Length属性<br>
 字符串对象的创建方式：<br>
 单引号创建：var str=’hello world!’;<br>
 双引号创建：var str=”hello world!”;<br>
 New关键字创建：var str=new String(“字符串内容”)<br>
 Length用来求字符串对象的长度：var str=’aaa’   alert(a.length)  弹出3<br><br>

当然还有很多简单举例<br>
charAt()：方法返回一个给定位置的字符，超出有效范围的索引值返回空字符串。<br>
例如：var str=’hello world!’ alert(str.charAt(1))  弹出e<br>
indexOf()：方法返回给定字符串第一次出现的位置，是一个整数。如果没有找到子字符串，则返回 -1。<br>
例如：var str=’he’ alert(str.indeOf(‘A’))  				   弹出-1；<br>
var str=’hello’ alert(str.indeOf(‘e’))  弹出1<br>
lastIndexOf()：方法返回给定的字符串最后一次出现的位置，是一个整数。如果没有找到这个字符串，返回为-1。<br>
例如：var str=”hello world!”  alert(str.lastIndexOf(‘l’))   弹出9<br>
Split()：将字符串分割成数组，将结果作为字符串数组返回。<br>
例如：var s = "The rain in Spain falls mainly in the plain.";<br>
   // 在每个空格字符处进行分解。<br>
   ss = s.split(" ");<br>
   alert(ss)<br>
Substr(开始位置,截取长度)：字符串截取，返回一个从开始位置到指定长度的截取后的字符串，长度可省。<br>
例如：var str='hello world!'alert(str.substr(3,2))   //弹出lo<br>
Substring(开始位置，结束位置)：字符串截取，返回一个从开始位置到结束位置的截取后的字符串。<br>
例如：Var str=’hello world!’alert(str.substring(1,3)) //弹出el  注意：不包含结束位置的字符<br>
<br>
Date对象的基本操作方法<br>
  Date()：返回系统当前的日期和时间<br>
  getDate()：从日期对象中返回一个月中的某一天<br>
  getDay()：从日期对象中返回一周中的某一天<br>
  getMonth()：从日期对象中返回月份<br>
  getYear()：从日期对象中返回年份<br>
  getHours()：从日期对象中返回小时<br>
  getMinutes()：从日期对象中返回分钟<br>
  getSeconds()：从日期对象中返回秒数<br>
  getTime()：返回从1970年1月1日至今的毫秒数<br>
  toLocaleString()：根据本地时间格式，把日期对象转换为字符串<br><br>

DOM编程的基本找对象方法<br>
 1）通过id找对象：document.getElementById(“元素id”)<br>
 2）通过name找对象：document.getElementsByName(“元素name”)<br>
 3）通过标签找对象：document.getElementsByTageName(“标签名”)<br>
 4）通过forms找对象：document.forms[0]找到html文档中第一个表单，[]里的下标也可以写成表单的name属性<br><br>

我们再谈下 js正则<br>
定义：正则表达式是由一系列普通字符和特殊字符组成的能明确描述文本字符的文字匹配模式<br>
作用：验证表单数据的有效性，js的客户端验证大大提高了用户体验，增强数据的有效性，可以减轻php工作的压力。<br>
声明方式：var 变量名=/^正则表达式$/<br><br>

正则表达式的匹配符<br>
\：转义字符  例如：\b转义了b<br>
^：正则表达式开始符号<br>
$：正则表达式结束符号<br>
*：匹配前面的字符出现0次或者n次<br>
+：匹配前面的字符出现1次或者n次<br>
?：匹配前面的字符出现0次或者1次<br>
.：匹配除了换行符以外的所有单个字符<br>
|：或者的意思，例如x|y  匹配x或者y<br>
{n}：匹配前面的n个字符<br>
{n,m}：匹配至少n个最多m个前面字符<br>
[xyz]：匹配中括号里的任意一个字符<br>
[^xyz]：匹配除了中括号里的任意一个字符等价于[0-9]<br>
\w：匹配任意一个数字或字母或下划线 等价于[A-Za-z0-9_]<br>
\d：匹配任意一个0--9之间的数字<br>
模式修正符：<br>
i：忽略大小写<br><br>

正则检测字符串函数：test()，成功返回true，失败返回false<br><br>

来个简单例子吧 <br>
例如：<br>
Var str=”zhangsan”;<br>
Var reg=/^\w+$/;<br>
If(reg.test($str)){<br>
 	alert(“用户名合法”)<br>
}<br><br>

常用正则表达式举例：<br>
//用户名由6-18位的字母数字下划线组成，不能由数字开头<br>
var r_name=/^[a-z]\w{5,17}$/i<br>
//密码长度不能少于六位<br>
var r_pwd=/^\w{6,}$/<br>
//验证手机号:11位  13 15 18开头<br>
var r_tel=/^1[3,5,8]\d{9}$/<br><br><br>


当然 我们这里还需要写下ajax <br>
ajax是一种技术，它是由div+css javascript和xml技术组成<br>
作用：异步存取，局部刷新，能实现无页面刷新的效果<br>
Ajax优点：可以减轻服务器处理数据的压力，实现无页面刷新，增强用户体验。<br>
Ajax缺点：不利于SEO（搜索引擎）优化<br>
Ajax应用场景：在页面显示大量数据，实时更新的网站上，实现局部刷新<br><br>

ajax的运行原理<br>
客户端浏览器通过ajax引擎发送请求，服务器接收请求后通过php访问数据库处理数据，处理完的数据通过ajax引擎响应给客户端，客户端通过js把数据放到需要的地方。<br>
		客户端<br>
    请求  |  |  响应<br>
       ajax引擎<br>
          |  |<br>
    Web服务器apache<br>
      访问|  |返回<br>
         数据库<br><br>

ajax的核心代码<br>
a.ajax对象：var ajax= new XMLHttpRequest();<br>
b.ajax属性<br>
1)readyState：ajax对象的准备状态，状态从0----4发生变化<br>
　　	0：请求未初始化<br>
　　	1：服务器连接已建立<br>
　　	2：请求已接收<br>
　　	3：请求处理中<br>
　　	4：请求已完成且响应已就绪<br>
2)responseText：响应文本  <br>
3)status状态： 值为200表示处理成功<br>
值为404表示没有找到处理文件<br>
c.ajax事件 onreadystatechange<br>
d.ajax方法<br>
1)ajax.open()：与服务器建立连接（get（提交方式 url（地址） true（异步））<br>
2)ajax.send()：处理请求<br>
例如：<br>
  Get方式请求：<br>
//1.创建ajax对象<br>
var ajax= new XMLHttpRequest();<br>
//2.ajax事件<br>
ajax.onreadystatechange = function(){<br>
if(ajax.readyState ==4) {<br>
//处理语句<br>
} <br>
}<br>
//3.与服务器建立连接<br>
ajax.open('get',url,false);<br>
//4. 服务器处理请求<br>
ajax.send(null);<br><br>

现在就先到这里 留下当时学习的经过…………<br><br>