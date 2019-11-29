# 课程目标和定位

> 掌握html语义化标签，能够使用html和css实现静态网站的搭建

## 第一章 Web 介绍

> 学习web前端开发基础技术需要掌握三门技术：HTML、CSS、JavaScript语言。下面我们就来了解下这三门技术都是用来实现什么的

### 第一节 HTML

- HTML是网页内容的载体。内容就是网页制作者放在页面上想要让用户浏览的信息，可以包含文字、图片、视频等。
- HTML 指的是超文本标记语言 (**H**yper **T**ext **M**arkup **L**anguage)。
- HTML 不是一种编程语言，而是一种标记语言 (markup language) 
- 标记语言是一套标记标签 (markup tag) 

### 第二节 CSS

- CSS样式是表现。就像网页的外衣。比如，标题字体、颜色变化，或为标题加入背景图片、边框等。所有这些用来改变内容外观的东西称之为表现。
- CSS全称为  “层叠样式表 (Cascading Style Sheets)”

### 第三节 JavaScript

- JavaScript是用来实现网页上的特效效果。如：鼠标滑过弹出下拉菜单。或鼠标滑过表格的背景颜色改变。还有焦点新闻（新闻图片）的轮换。可以这么理解，有动画的，有交互的一般都是用JavaScript来实现的。

## 第二章 HTML 标签

### 第一节 什么是HTML标签

- HTML 标签是由`<>`包围的关键词，比如`<html>`
- HTML 标签通常成对出现，分为标签开头和标签结尾`<html> </html>`
- 页面中所有的内容，都要放在HTML标签中
- HTML标签主体分为三个部分
  - 标签名称
    - 写在`<>`中间的英文单词就是标签的名称，如`<div></div>` 标签中的`div`就是标签名
  - 标签内容 
    - 标签的内容就是在一对标签内部的内容
    - 标签的内容可以是文本，图片，音频，视频，也可以是html标签
  - 标签属性
    - 和标签名称一起写在`<>`内部的就是标签的属性
    - `<img src="img01.jpg"/>`href是标签的属性
    - `<a href="http://www.baidu.com"></a>`
- HTML 标签具有语义化
  - 语义化：说的通俗点就是，明白每个标签的用途（在什么情况下我可以使用这个标签才合理）比如，网页上的文章的标题就得用标题标签，网页上的各个栏目的栏目名称也可以使用标题标签。网页中大段的文字，使用段落标签。
  - 语义化的作用
    -  更容易被搜索引擎收录。
    -  更容易让屏幕阅读器读出网页内容。

## 第三章 HTML标签介绍

### 第一节 文本标签

> 学习完本小节，可以了解不同文本标签的作用

#### 1. 段落标签  `<p></p>`

- 段落标签用来描述一段文字

#### 2. 标题标签  `<hx></hx>`

- 标题标签用来描述一个标题
- 标题标签总共有六个级别，由高到低分别是h1,h2,h3,h4,h5,h6

```html
<h1>我是一级标题</h1>
<h2>我是二级标题</h2>
<h3>我是三级标题</h3>
<h4>我是四级标题</h4>
<h5>我是五级标题</h5>
<h6>我是六级标题</h6>
```

- `<h1></h1>`标签在每个页面中通常只出现一次

#### 3. 斜体标签`<em></em>`

- 用于强调某些文字的重要性，文字默认斜体

#### 4. 粗体标签`<strong></strong>`

- 用于强调某些文字的重要性，其重要性比em标签大，文字加粗

#### 5. 万能标签`<span></span>`

- <span>标签是没有语义的，它的作用就是为了设置单独的样式用的，把一段话圈起来，然后用css设置样式。

#### 6. 短文本引用标签`<q></q>`

- 简短文字的引用

#### 7. 换行标签`<br/>`

- `<br/>`标签作用相当于word文档中的回车,起到文字换行的作用
- `<br/>`中间不需要写内容，所以只写一个标签即可，不需要成对出现，这种标签叫做单标签

#### 8. 横线 `<hr/>`

- 在页面中显示成一条横线


### 第二节 多媒体标签

#### 1. 链接标签 `<a></a>`

- `<a href="http://www.hxsd.com" target="_blank"></a>`
- href属性：描述了链接的目标。
- target属性：定义被链接的文档在何处显示。
  - _blank 新在新的页面打开
  - _parent 在父容器中打开页面
  - _self 从本页面打开
  - _top 从最顶层打开
- 锚点连接，页面内，点击页面，可以跳转到页面指定元素位置
- 在a连接写href="#xxx", 指定元素写 id="xxx";
- a连接写` href="#" `，会实现假连接效果，但是点击后，页面会跳转到最顶端
- ` href="##"` 或者 `<a href="javascript:;">`可以实现假连接效果，并且不会跳转到页面最顶端

#### 2. 图片标签 `<img/>`

- `<img src="img01.jpg" title="" alt=""/> `


- src属性：用来设置图像，音频，视频文件所在位置。
- title属性：鼠标移入图片，显示的提示信息
- alt属性：当图片加载失败，显示的文字信息

#### 3. 视频标签`<video></video>`

- ```
  <video src="mov.mp4" controls="controls">
  ```

- 目前video支持三种视频格式

  - Ogg = 带有 Theora 视频编码和 Vorbis 音频编码的 Ogg 文件
  - MPEG4 = 带有 H.264 视频编码和 AAC 音频编码的 MPEG 4 文件
  - WebM = 带有 VP8 视频编码和 Vorbis 音频编码的 WebM 文件

- controls属性：是否显示控制条

- autoplay属性：是否自动播放

- loop属性：是否循环播放

- poster：默认显示的图片

- muted：静音

#### 4. 音频标签`<audio></audio>`

- `<audio src="a01.mp3"></audio>`
- controls属性：是否显示控制条
- autoplay属性：是否自动播放

### 第三节 列表标签

> 掌握标签间的

#### 1. 无序列表标签`<ul><li><li/></ul>`

- ul-li是没有前后顺序的信息列表
- `<ul><ul/>`列表定义一个无序列表
- `<ul><li><li/></ul>`必须搭配使用，一个ul里面可以有多个li
- `<li><li/>`代表无需列表中的每一个元素
- 无序列表中的每个li在浏览器中默认带一个实心小圆点，如果我们不需要，可以通过css样式去除

```html
<ul>
  <li>HTML<li/>
  <li>CSS<li/>
  <li>JavaScript<li/>
</ul>
```

#### 2. 有序列表`<ol><li><li/></ol>`

- ol-li列表默认情况下，每个li在浏览器中都会显示一个数字，代表自己的序号
- 可以通过css样式去除掉默认样式

#### 3. 定义列表`<dl></dl>`

- 定义列表通常和`<dt></dt>`和`<dd></dd>`标签一起使用
- `<dt></dt>`定义列表中的项目
- `<dd></dd>`描述列表中的项目

```html
<dl>
  	<dt>学习WEB前段需要掌握哪三种语言</dt>
  	<dd>需要掌握HTML，搭建网页结构</dd>
  	<dd>需要掌握CSS，用于修改网页结构的样式</dd>
  	<dd>需要掌握JavaScript，用于用户和计算机交互</dd>
</dl>
```

### 第四节 表格标签系列

#### 1. 表格标签`<table></table>`

#### 2. 表格的一行`<tr></tr>`

- 有几对tr, 表格就有几行。

#### 3. 表格的表头`<th></th>`

- 表格的头部的一个单元格，表格表头。

#### 4. 单元格`<td></td>`

- 表格的一个单元格，一行中包含几对`<td><td/>`，说明一行中就有几列。

```html
<table>
	<tr>
		<th>姓名</th>
		<th>性别</th>
		<th>年龄</th>
	</tr>
	<tr>
		<td>张三</td>
		<td>男</td>
		<td>25</td>
	</tr>
	<tr>
		<td>小花</td>
		<td>女</td>
		<td>23</td>
	</tr>
	<tr>
		<td>李四</td>
		<td>男</td>
		<td>28</td>
	</tr>
</table>
```

#### 5. 表格合并

- 同一行内，合并																																	··几列`colspan=“2”`
- 同一列内，合并几行`rowspan="3"`

### 第五节 其他语义化标签

#### 1. 盒子`<div></div>` 

- 俗称为盒子，division（分割）
- 在网页制作过程过中，可以把一些独立的逻辑部分划分出来，放在一个<div>标签中，这个<div>标签的作用就相当于一个容器。
- 什么是逻辑部分？它是页面上相互关联的一组元素。如网页中的独立的栏目版块，就是一个典型的逻辑部分。

#### 2. 网页头部`<header></header>`  

- HTML5新增语义化标签，定义网页的头部
- 主要用于布局，分割页面的结构

#### 3. 底部信息`<footer></footer>`  

- HTML5新增语义化标签，定义网页的底部
- 主要用于布局，分割页面的结构

#### 4. 导航`<nav></nav>` 

-  HTML5新增语义化标签，定义一个导航
-  主要用于布局，分割页面的结构

#### 5. 文章`<article></article> ` 

- HTML5新增语义化标签，定义一篇文章
- 主要用于布局，分割页面的结构

#### 6. 侧边栏`<aside></aside>` 

- 语义化标签，定义主题内容外的信息
- 主要用于布局，分割页面的结构

#### 7. 时间标签`<time></time>`

- 语义化标签，定义一个时间

### 第六节  表单标签系列

#### 1. 表单标签`<form></form>` 

- `<form></form>`表单是可以把浏览者输入的数据传送到服务器端，这样服务器端程序就可以处理表单传过来的数据。
- `<form method="传送方式" action="服务器文件">`
- action属性 ：浏览者输入的数据被传送到的地方,比如一个PHP页面(save.php)
- method属性 ： 数据传送的方式（get/post）

#### 2. `<input/>`文本输入框

- 当用户要在表单中键入字母、数字等内容时，就会用到文本输入框。文本框也可以转化为密码输入框。
- `<input type="text" name="名称" value="请输入" />`
- type:当`type="text"`时，输入框为文本输入框;
- name：为文本框命名，以备后台程序ASP 、PHP使用。
- value：为文本输入框设置默认值。(一般起到提示作用)

####  3. `<input/>`密码输入框

- `<input type="password" name="名称" value="请输入密码" />`


- 当`type="password"`时, 输入框为密码输入框,此时界面不会显示用户输入的文字，而是以实心黑点代替。

#### 4.  `<input/>`单选框

```html
<input type="radio" name="color" value="red" checked="checked" />红色
<input type="radio" name="color" value="blue" />蓝色
<input type="radio" name="color" value="pink" />粉色
```

- 单选框，用户在众多选项里，只可以选择一个选项
- 同一组的单选按钮，name取值一定要一致，这样同一组的单选按钮才可以起到单选的作用。
- name：为控件命名，以备后台程序ASP、PHP使用
- checked：当设置checked="checked"时，该选项被默认选中

#### 5.  `<input/>`复选框

```html
<input type="checkbox" name="color" value="red" />红色
<input type="checkbox" name="color" value="blue" checked="checked"/>蓝色
<input type="checkbox" name="color" value="pink" />粉色
```

- 复选框，用户在众多选项里，可以选择多个选项
- name：为控件命名，以备后台程序ASP、PHP使用
- checked：当设置checked="checked"时，该选项被默认选中

#### 6.  `<input/>`提交按钮

- `<input type="submit" value="提交按钮" />`
  - 用户点击提交按钮后，会把form表单中的数据提交到后台
- `<input type="reset" value="重置按钮" />`
  - 用户点击提交按钮后，会把form表单内容重置
- `<input type="button" value="普通按钮" />`
- value：按钮的显示文字

#### 7.  `<input/>`重置按钮

- `<input type="reset" value="重置" />`

#### 8. 下拉选择框`<select><select/>`

```html
<select>   
    <option value="看书">看书</option>      
    <option value="旅游" selected="selected">旅游</option>    
    <option value="运动">运动</option>     
    <option value="购物">购物</option>	   
</select>
```

- `<option value="提交值">选项</option>`是下拉选择框里面的每一个选项
- selected：当某个option选项有这个属性时候，select默认选中这个选项

#### 9. 文本域 `<textarea></textarea>`

- 当用户想输入大量文字的时候，使用文本域
- cols属性 ：多行输入域的列数。
- rows属性 ：多行输入域的行数
- 文本域默认状态是可以用户通过鼠标调整大小，如果不想用户调整，可以使用css样式禁止

#### 10. 按钮`<button></button>`

- `<button type="button">按钮</button>`
- type=button 没有默认功能，知识一个按钮
- type=submit 具有提交功能的按钮
- type=reset 具有重置表单的功能

#### 11. 扩大选区`<label></label>`

- 可以扩大单选框和复选框的点击范围

```html
点击文字也可以实现效果
<label><input type="radio" name="sex"/>男</label>
<label><input type="radio" name="sex"/>女</label>

<input type="radio" name="aaa" id="a2"/><label for="a2">红</label>
<input type="radio" name="aaa" id="a1"/><label for="a1">绿色</label>
```



## 第四章 页面结构与模块划分

### 第一节 网页结构

- 一个HTML文件是有自己固定的结构的。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
	</body>
</html>
```

- `<!DOCTYPE html>` 定义文档类型，告知浏览器用哪一种标准解释HTML
- `<html></html>`可告知浏览器其自身是一个 HTML 文档。
- `<head></head> `标签用于定义文档的头部，它是所有头部元素的容器。头部元素有`<title>、<script>、<style>、<link>、<meta>`等标签.
- `<body></body>`标签之间的内容是网页的主要内容，如`<h1>、<p>、<a>、<img>`等网页内容标签，在这里的标签中的内容会在浏览器中显示出来。
- `<title></title> `元素可定义文档的标题。
- `<link>`标签将css样式文件链接到HTML文件内
- `<meta>`定义文档的元数据，网页的元信息（charset=“utf-8” 国际编码类型）

### 第二节 模块划分

- 每个网页都是由不同的功能模块组成的，因此在将制作网页的时候，我们要将网页的每个功能模块分开
  -  常见的企业站，多由头部区，展示图片区域，主体区域，底部信息区域组成


- 网页拆分原则
  - 由上到下
  - 由外带内
  - 由左到右
- div header footer nav article aside等标签多用于模块划分

## 第五章 CSS 概述

### 第一节 CSS代码语法

- CSS全称为“层叠样式表 (Cascading Style Sheets)”，它主要是用于定义HTML内容在浏览器内的显示样式，如文字大小、颜色、字体加粗等。
- css代码通常存放在`<style></style>`标签内
- css 样式由选择符和声明组成，而声明又由属性和值组成
- `选择符{属性:值}`如：`p{color:red;}`
- 选择符：又称选择器，指明网页中要应用样式规则的元素
- 声明：在英文大括号`｛｝`中的的就是声明，属性和值之间用英文冒号`：`分隔。当有多条声明时，中间可以英文分号`;`分隔，如：

```css
p{
  font-size:12px;
  color:red;
}
```

### 第二节 CSS 放置位置

#### 1. 行内样式

- 直接书写在标签的style属性中
- 不建议使用

```html
<div style="width:200px; height:200px;"></div>
```

#### 2. 内联式样式表

- 写在`<style></style>`标签中

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style>
			.box{
              	width:200px;
              	height:200px;
              	background-color:red;
			}
		</style>
	</head>
	<body>
	</body>
</html>
```

#### 3. 外联样式表

- 将一个独立的.css文件引入到HTML文件中，使用<link>标记写在<head>标记中。 链接式会以网页文件主体装载前装载CSS文件。
- `rel="stylesheet"`定义类型为层叠样式表，一定要写

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<link href="My.css" rel="stylesheet" type="text/css">
	</head>
	<body>
	</body>
</html>
```

### 第三节 CSS的继承

- CSS的某些样式是具有继承性的，那么什么是继承呢？继承是一种规则，它允许样式不仅应用于某个特定html标签元素，而且应用于其后代。
- 不可继承样式：display、margin、border、padding、background、height、min-height、max-height、width、min-width、max-width、overflow、position、left、right、top、bottom、z-index、float、clear
- 可以继承的样式：letter-spacing、word-spacing、white-space、line-height、color、font、font-family、font-size、font-style、font-variant、font-weight、text-decoration、text-transform、direction、visibility、cursor

## 第六章 CSS 选择器

### 第一节 选择器的种类

#### 1. 标签选择器

- 通过标签的名字，修改css样式

```css
div{
  	width:200px;
  	height:300px;
}
```

#### 2. id选择器

- 通过id查找页面中唯一的标签，在结构中只能使用一次

```css
#wrap{
  	width:200px;
  	height:300px;
}
```

#### 3. class选择器

- 通过特定的class来查找页面中对应的标签
- 以英文的句号开头，后面跟随class的名称

```css
.box{
  	width:200px;
  	height:300px; 	
}
<div class="box"></div>
```

 ####4. 群组选择器

- 可以对多个不同的选择器设置相同的样式

```css
.box,.box1,.box2{
  	width:200px;
  	height:300px;
}
.box h1,.box1 h2,.box2 .txt{
  	width:200px;
  	height:300px;
}
```

#### 5. 后代选择器

- 选择某个父元素下面所有的元素

```css
.box p{
  	background-color:red; 	
}
```

#### 6. 一级子元素选则器

- 选择某个父元素的直接子元素
- 后代选择器是选择父元素的所有子孙元素，一级子元素原则器只选择第一级子元素，不会再向下查找元素

```css
.box>p{
  	background-color:red; 	
}
```

#### 7. `*`通配符选择器

- 选择页面中所有的元素

```css
*{
  	margin:0;
  	padding:0;
}
```

#### 8. 伪类选择器

- `:hover`鼠标移入某个元素

```html
.box:hover{
  	color:red;
}
```

- `:before`在某个元素的前面插入内容

```css
div:before{
  	content:"- 台词";
    background-color:yellow;
    color:red;
    font-weight:bold;
}
```

- `:after`在某个元素的后面插入内容

```css
div:after{
  	content:"- 台词";
    background-color:yellow;
    color:red;
    font-weight:bold;
}
```

### 第二节 选择器的优先级

- 当有不同的选择器对同一个对象进行样式指定时，并且两个选择器有相同的属性被赋予不同的值时。
- 通过测算那个选择器的权重值最高，应用哪一个选择器的样式
- 权重计算方式：
  - 行内样式：A
  - id选择器：B
  - class选择器：C
  - 标签选择器：D
  - !important 最高级别，提高样式权重，拥有最高级别（尚方宝剑）

 ```css
p{width:200px}		/*权重 0001*/
.box{width:200px}		/*权重 0010*/
.box p{width:200px}		/*权重 0011*/
#txt{width:200px}		/*权重 0100*/
 ```

- 如果两个选择器的权重值一样高，则应用距离对象最近的css样式

## 第七章 浮动和定位

### 第一节 浮动 `float`

> 块级元素默认是独占一行，所以页面都会自上而下的排列
>
> 如果现在我们想让两个块状元素并排显示，设置元素浮动就可以实现这一愿望。
>
> 任何元素在默认情况下是不能浮动的，但可以用CSS定义为浮动

#### 1. 设置浮动

- 想要让几个元素水平向左布局，可以给每个元素定义左浮动`float:left;`
- 想要让几个元素水平向右布局，可以给每个元素定义左浮动`float:right;`
- 浮动的元素会脱离文档流
- 设置浮动的元素，宽度会变成自适应


- 设置浮动的同时一定要先设置块级父元素元素的宽度，且需要浮动的几个元素宽度加起来一定要小于父元素的宽度。

#### 2. 清除浮动带来的影响

- clear 清除浮动：
  - none  :  默认值。允许两边都可以有浮动对象
  - left   :  不允许左边有浮动对象
  - right  :  不允许右边有浮动对象
  - both  :  不允许两边有浮动对象
- 利用伪类实现清除浮动

```css
.clearFix{
  	content="";
  	display:block;
  	width:0;
  	height:0;
  	clear:both;
}
```



### 第二节 定位`position` 

> 浮动布局解决了元素的排列问题；但有些元素相互为重叠，这时就需要用到定位了。

#### 1. 层模型--绝对定位

>  如果想为元素设置层模型中的绝对定位，需要设置position:absolute(表示绝对定位)，这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。如果不存在这样的包含块，则相对于body元素，即相对于浏览器窗口。

- `position:absolute;`
- 绝对定位是相对于有定位属性的父元素

```css
div{
    width:200px;
    height:200px;
    border:2px red solid;
    position:absolute;
    left:100px;
    top:50px;
}
/*实现div元素相对于浏览器窗口向右移动100px，向下移动50px。*/
```

#### 2.层模型--相对定位

> 如果想为元素设置层模型中的相对定位，需要设置position:relative（表示相对定位），它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。

- `position:relative;`
- 相对定位是相对于文档流中自己的位置

```css
#div1{
    width:200px;
    height:200px;
    border:2px red solid;
    position:relative;
    left:100px;
    top:50px;
}
/*相对于以前位置向下移动50px，向右移动100px;*/
```

#### 3. 层模型--固定定位 

> 与absolute定位类型类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，除非你在屏幕中移动浏览器窗口的屏幕位置，或改变浏览器窗口的显示大小，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响.

- `position:fixed`
- 相对于与浏览器视口定位

#### 4. 绝对定位和相对定位搭配使用
>  使用position:absolute可以实现被设置元素相对于浏览器（body）设置定位以后，大家有没有想过可不可以相对于其它元素进行定位呢？答案是肯定的，当然可以。
>  如果我们想让一个元素A相对于元素B定位，那么可以让元素B的position定义成relative，再让元素A的positon属性定义成absolute

#### 5. 层级关系 z-index

> 有了定位属性的元素，会覆盖住没有定位属性的元素。
>
> 如果两个元素都有定位属性，那要通过设置z-index属性来确定谁在上一层

- `z-index:10`

## 第八章 css样式

### 第一节 基本样式

#### 1. 宽度`width`

- `width:200px;`


- 定义元素的宽度

#### 2. 高度`height`

- `height:300px`


- 元素默认没有高度
- 需要设置高度
- 可以不定义高度，让元素的内容将元素撑高

#### 3. 鼠标样式`cursor `

- 定义鼠标的样式`cursor:pointer`
  - `  default`默认
  - `  pointer`小手形状
  - `move`移动形状

#### 4. 透明对`opacity`

- `opacity:0.3`
- 透明度的值可以使0~1之间的数字，0代表透明，1代表完全不透明
- 透明的元素，知识看不到了，但是还占据着文档流

#### 5. 可见性`visibility`

- `visibility:hidden; `
- visible 元素可见
- hidden 元素不可见
- collapse 当在表格元素中使用时，此值可删除一行或一列，不会影响表格的布局。

#### 6. 溢出隐藏 `overflow` 

- 设置当对象的内容超过其指定高度及宽度时如何显示内容
- visible 默认值，内容不会被修剪，会呈现在元素框之外。
- hidden 内容会被修剪，并且其余内容是不可见的。
- scroll 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。
- auto 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。

#### 7. 边框颜色`outline`

- input文本输入框自带边框，且样式丑陋，我们可以通过outline修改边框
- `outline:1px solid #ccc`;
- `outline:none`清除边框

### 第二节 字体样式

#### 1. 字体族`font-family`

- `font-family:"微软雅黑","黑体";  `
- 使用逗号隔开多种字体（优先级从前向后，如果系统中没有找到当前字体，则往后面寻找）

#### 2.字体大小`font-size` 

- `font-size:12px;`


- 网页默认字体大小是16px

#### 4. 字体粗细`font-weight`

- `font-weight:400`;


- normal（默认）
- bold（加粗）
- bolder（相当于<strong>和<b>标签）
- lighter （常规）
- 100 ~ 900 整百（400=normal，700=bold）

#### 5. 字体颜色`color`

- 颜色的英文单词`color:red;`
- 十六进制色：`color: #FFFF00; `
- RGB(红绿蓝)`color:rgb(255,255,0)`
- RGBA（红绿蓝透明度）A是透明度在0~1之间取值。`color:rgba(255,255,0,0.5)`

#### 6. 字体斜体`font-style`

- `font-style:italic  `


- normal  文本正常显示
- italic  文本斜体显示
- oblique  文本倾斜显示

#### 7. font简写

- 字体样式可以简写，书写顺序“font-style font-weight font-size/line-height font-family"
- font-size和font-family的值是必需的

```css
body{
  font:italic normal 12px/24px "Microsoft YaHei",arial;
}
```

### 第三节 文本属性

#### 1. 行高`line-height`

- `line-height:50px;`
- 可以将父元素的高度撑起来

#### 2. 文本水平对其方式`text-align`

- left 左对齐
- center 文字居中
- right 右对齐

#### 3. 文本所在行高的垂直对齐方式`vertical-align`

- baseline 默认
- sub 垂直对齐文本的下标，和<sub>标签一样的效果
- super 垂直对齐文本的上标，和<sup>标签一样的效果
- top 对象的顶端与所在容器的顶端对齐
- text-top 对象的顶端与所在行文字顶端对齐
- middle 元素对象基于基线垂直对齐
- bottom 对象的底端与所在行的文字底部对齐
- text-bottom 对象的底端与所在行文字的底端对齐

#### 4. 文本缩进`text-indent`

- `text-indent:2em;`


- 通常用在段落开始位置的首行缩进

#### 5. 字母之间的间距`letter-spacing`

- 汉字域汉字 英文字母与英文字母之间的间距

#### 6. 单词之间间距`word-spacing`

- 中文词组之间的间距 
- 英文单词 与 单词之间的间距

#### 7.文本的大小写`text-transform`

- capitalize 文本中的每个单词以大写字母开头。
- uppercase 定义仅有大写字母。
- lowercase 定义仅有小写字母。

#### 8. 文本的装饰`text-decoration`

- none 默认。
- underline 下划线。
- overline 上划线。
- line-through 中线。

#### 9. 自动换行

```css
1. word-break:break-all;只对英文起作用，以字母作为换行依据
2. word-wrap:break-word; 只对英文起作用，以单词作为换行依据
3. white-space:pre-wrap; 只对中文起作用，强制换行
4. white-space:nowrap; 强制不换行，都起作用

5. white-space:nowrap; overflow:hidden; text-overflow:ellipsis;不换行，超出部分隐藏且以省略号形式出现（部分浏览器支持） 

代码：
.p1{ word-break:break-all; width:150px;}/*只对英文起作用，以字母作为换行依据*/
.p2{ word-wrap:break-word; width:150px;}/*--只对英文起作用，以单词作为换行依据*/
.p3{white-space:pre-wrap; width:150px;}/*只对中文起作用，强制换行*/
.p4{white-space:nowrap; width:10px;}/*强制不换行，都起作用*/
.p5{white-space:nowrap; overflow:hidden; text-overflow:ellipsis; width:100px;}／/*不换行，超出部分隐藏且以省略号形式出现*/
```

### 第三节 背景样式

#### 1. 背景颜色`background-color`

- `background-color:red`
- 背景颜色的值可以是英文，可以是十六进制颜色值，可以是rgb，也可以是rgba

#### 2. 背景图片`background-image`

- `background-image:url(bg01.jpg);`
- 背景图片的大小可以和容器大小不一样
- 背景图片不会占位
- 如果容器大，背景图片小，背景图片会平铺 铺满整个容器

#### 3. 背景图片位置`background-position`

- `background-position:10px 100px;`
- 背景图片定位的值是两个单位，分别代表坐标x，y轴
- 背景图片定位的值可以是应为left，right，top，bottom，center
- 背景图片定位的值也可以是百分比或者像素

#### 4. 背景图片重复`background-repeat `

- `background-repeat:no-repeat`


- no-repeat 设置图像不重复，常用
- round 自动缩放直到适应并填充满整个容器
- space 以相同的间距平铺且填充满整个容器
- repeat-x x轴平铺
- repeat-y y轴平铺

#### 5. 背景图片定位`background-attachment`

- `background-attachment:fixed`


- 背景图像是否固定或者随着页面的其余部分滚动
- `background-attachment`的值可以是scroll（跟随滚动），fixed（固定）

#### 6. `background`缩写

- `background:#ff0000 url(bg01.jpg) no-repeat fixed center`

#### 7. 精灵图技术

> 我们在做前端页面的时候，网页中通常包含有很多小图标，这就用到了css sprites技术。把所有小图标放到一张图上，这样可以减少对服务器的请求次数。

### 第四节 盒模型样式

#### 1. HTML元素分类

> 在讲解CSS布局之前，我们需要提前知道一些知识，在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素和内联块状元素。

- html中的标签元素大体被分为三种不同的类型：块状元素、内联元素（行级元素）和内联块状元素。

- 块级元素特点：
  1、每个块级元素都从新的一行开始，并且其后的元素也另起一行。
  2、元素的高度、宽度、行高以及顶和底边距都可设置。
  3、元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。

- 行内元素特点：
  1、和其他元素都在一行上；
  2、元素的高度、宽度、行高及顶部和底部边距不可设置；
  3、元素的宽度就是它包含的文字或图片的宽度，不可改变。

- 内联块状元素特点：

  1、和其他元素都在一行上；
  2、元素的高度、宽度、行高以及顶和底边距都可设置。

- 块级标签汇总

  - `<div>`、`<p>`、`<h1>`到`<h6>`、`<ol>`、`<ul>`、`<dl>`、`<table>`、`<address>`、`<blockquote>` 、`<form>`

- 行级标签汇总

  - `<a>`、`<span>`、`<br>`、`<i>`、`<em>`、`<strong>`、`<label>`、`<q>`

- 内联块状元素汇总

  - `<img>`,`<input>`

#### 2. 元素分类转换`display`

- block：将元素转换为块级元素
- inline：将元素装换为行级元素
- inline-block：将元素转换为内联块元素
- none: 将元素隐藏

#### 3. 描边`border`

- `border:2px solid #f00`;


- 盒子模型的边框就是围绕着内容及补白的线，这条线你可以设置它的粗细、样式和颜色(边框三个属性)。
- 线条的样式：
  - dashed（虚线）| dotted（点线）| solid（实线）。
- css样式中允许只为一个方向的边框设置样式：
  - 下描边`border-bottom:1px solid red;`
  - 上描边`border-top:1px solid red;`
  - 右描边`border-right:1px solid red; `
  - 左描边`border-left:1px solid red;`

#### 4. 间距`margin`

- `div{margin:20px 10px 15px 30px;}`
- 元素与其它元素之间的距离可以使用边界（margin）来设置。边界也是可分为上、右、下、左。
- 也可以分开写：

```css
div{
   margin-top:20px;
   margin-right:10px;
   margin-bottom:15px;
   margin-left:30px;
}
```

- 当margin给一个值时：指的是四个方向

- 当margin有两个值时：指的是上下   左右

- 当margin给三个值时：指的是上   左右   下

- 当margin给四个值时：值的是上   右   下   左

- margin-top的小bug

  - 当父元素嵌套子元素垂直排排列时，他们的margin-top就会取其中一个margin-top的最大值，导致父元素的整体下移

  - 有三种解决办法：

    1.给父元素加一个边框

    2.给父元素加overflow:hidden;属性

    3.取消子元素的margin-top，父元素使用padding-bottom

#### 5. 内填充`padding`

- `padding:10px`
- 元素内容与边框之间是可以设置距离的，称之为填充。填充也可分为上、右、下、左。
- 如下代码：`div{padding:20px 10px 15px 30px;}`
- 顺序一定不要搞混。可以分开写上面代码：

```css
div{
   padding-top:20px;
   padding-right:10px;
   padding-bottom:15px;
   padding-left:30px;
}
```

- 当padding给一个值时：指的是四个方向
- 当padding有两个值时：指的是上下   左右
- 当padding给三个值时：指的是上   左右   下
- 当padding给四个值时：值的是上   右   下   左

### 第五节 样式重置

> 早起的网页网页没有css样式，所以为了界面好看，很多元素都自带margin或者padding，但是这些属性每个浏览器解析的值都不一样，因此在现在，元素的默认样式给我们带来了很大的麻烦，现在只做网页，我们都会将css样式重置成一样的

- 清楚元素的margin和padding
- 去掉自带的列表符
- 去掉自带的下划线

```css
*{ margin:0; padding:0; }  /*清除页面所有标签自带的外间距和内填充*/
ul,ol{ list-style:none; }  /*去掉自带的列表符*/
a{ text-decoration:none; }  /*去掉自带的下划线*/
img,input{ border:none; } /*清除IE下自带的边框*/
```



## 第九章 CSS3 样式

### 第一节 过渡动画

- transition 过渡动画


- 语法：`transition: 样式 时间 速度函数 延迟时间;`
- 样式: 需要做过渡动画的样式，如果样式很多，可以写all 代表所有样式
- 速度函数：linear 匀速 |  ease 平滑过渡  | ease-in 加速 | ease-out 减速|ease-in-out  先加后减;

### 第二节 变形

- transform  变形


- rotate(); 旋转`rotate(30deg)   `
- scale(); 缩放`scale(1.5)` 
- translate(); 位移 `translate(150px,100px)`
- skew(); 倾斜`skew(50deg)  `

### 第三节 关键帧动画

- animation  关键帧动画


- 定义动画

```css
@Keyframes animateName{
       0%  { width:50px; }
       50% { width:10px; }
      100% { width:20px; }
}
```

- 应用动画

```css
.box{ animation: 动画名称 时间 速度函数 延迟时间 播放次数;  }
```

- 参数说明
  - 播放次数  infinite | number;   
  - animation-direction  normal | alternate;  (alternate 奇数次反向播放)
  - animation-fill-mode 属性定义在动画开始前和开始后的操作;
  - none 不改变默认行为; 
  - forwards 动画完成后停留在最后一帧;
  - backwards 有delay时动画开始应用起始帧属性;
  - both 同时具有forwards 和 backwards效果;

### 第四节 其他样式

#### 1. 阴影

- box-shadow: 0px 0px 0px 2px #000;


| 值          | 描述                        | 测试   |
| ---------- | ------------------------- | ---- |
| *h-shadow* | 必需。水平阴影的位置。允许负值。          |      |
| *v-shadow* | 必需。垂直阴影的位置。允许负值。          |      |
| *blur*     | 可选。模糊距离。                  |      |
| *spread*   | 可选。阴影的尺寸。                 |      |
| *color*    | 可选。阴影的颜色。请参阅 CSS 颜色值。     |      |
| inset      | 可选。将外部阴影 (outset) 改为内部阴影。 |      |

#### 2. 线性渐变

- background: linear-gradient(pink,skyblue);

```css
.box{
 	background: linear-gradient(pink,skyblue);	/*渐变开始和结束的两个值*/
	background: linear-gradient(to right,pink,skyblue);	/*渐变方向 ，渐变开始和结束的两个值*/
	background: linear-gradient(to right top,pink,skyblue);		/*坐下到右上 ，渐变开始和结束的两个值*/
  	/*渐变方向可以是角度，颜色可以用百分比调节过渡*/
	background: linear-gradient(180deg ,pink 0%,skyblue 20%,#0f0 100%);
}
```

#### 3. 径向渐变

- background: radial-gradient(center, shape, size, start-color, ..., last-color);
- center：渐变起点的位置，可以为百分比，默认是图形的正中心。
- shape：渐变的形状，ellipse表示椭圆形，circle表示圆形。默认为ellipse，如果元素形状为正方形的元素，则ellipse和circle显示一样。
- size：渐变的大小，即渐变到哪里停止，它有四个值。 closest-side：最近边； farthest-side：最远边； closest-corner：最近角； farthest-corner：最远角

```css
.box{
  background: -webkit-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); /* Safari 5.1 - 6.0 */
  background: -o-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); /* Opera 11.6 - 12.0 */
  background: -moz-radial-gradient(60% 55%, closest-side,blue,green,yellow,black); /* Firefox 3.6 - 15 */
  background: radial-gradient(60% 55%, closest-side,blue,green,yellow,black); /* 标准的语法（必须放在最后） */
}
```

#### 4 .圆角

- border-radius:10px;
- 一个值代表四周
- 两个值 分别代表   第一个值左上 右下 第二个值 右上和左下
- 三个值 分别代表   第一个值 左上 第二个值 右上和左下 第三个值 右下
- 四个值可以分别代表 左上  右上 右下 左下

## 附录

### 第一节 HTML 常用标签汇总

- `<style></style>`
- `<link/>`
- `<div></div>`
- `<p></p>`
- `<h1></h1>`
- `<h2></h2>`
- `<h3></h3>`
- `<h4></h4>`
- `<h5></h5>`
- `<h6></h6>`
- `<p></p>`
- `<em></em>`
- `<strong></strong>`
- `<span></span>`
- `<i></i>`
- `<b></b>`
- `<ul></ul>`
- `<li></li>`
- `<ol></ol>`
- `<dl></dl>`
- `<dt></dt>`
- `<dd></dd>`
- `<img/>`
- `<br/>`
- `<video></video>`
- `<audio></audio>`
- `<form></form>`
- `<input/>`
- `<select></select>`
- `<option></option>`
- `<textarea></textarea>`
- `<table></table>`
- `<tr></tr>`
- `<th></th>`
- `<td></td>`


### 第二节 常用的块级元素

- `<address>...</adderss>` 地址 
- `<h1>...</h1> ` 标题一级
- `<h2>...</h2>`  标题二级
- `<h3>...</h3>`  标题三级
- `<h4>...</h4>`  标题四级
- `<h5>...</h5>`  标题五级
- `<h6>...</h6>`  标题六级
- `<p>...</p>`  段落
- `<ul>...</ul>`  无序列表
- `<ol>...</ol>`  有序列表
- `<dl>...</dl>`  定义列表
- `<table>...</table>`  表格
- `<form>...</form>`  表单
- `<div>...</div>` 盒子

### 第三节 常用的行级元素

- `<span>...</span>`

- `<a>...</a>`  链接

- `<b>...</b>`  加粗

- `<strong>...</strong>`  加粗

- `<i>...</i>`  斜体

- `<em>...</em>`  斜体


