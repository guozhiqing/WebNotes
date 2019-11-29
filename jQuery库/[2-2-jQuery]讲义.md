---
categories:
	- jQuery
title: jQuery 教学讲义
author: 果志青
---

# 第一章 jQuery简介

## 第一节 jQuery是什么

- jQuery是一个JavaScript库，它通过封装原生的JavaScript函数得到一整套定义好的方法。
- 开发jQuery库的目的是——WRITE LESS,DO MORE（写的少，做的多）。它可以用最少的代码，完成更多复杂而困难的功能，从而得到了开发者的青睐。
- 它的作者是John Resig，于2006年创建的一个开源项目，随着越来越多开发者的加入jQuery已经集成了JavaScript、CSS、DOM和Ajax于一体的强大功能。

## 第二节 jQuery主要功能

- 一款轻量级的js库
- 丰富的DOM选择器
- 简单的事件操作
- 重新封装方法，让操作DOM属性更简单
- 链式操作
- 丰富的动画效果
- Ajax操作支持
- 浏览器兼容
- 插件扩展开发，可扩展性强

## 第三节 JQuery对象

- jQuery是一个构造函数，通过内置选择器对DOM元素进行“包装”，使之成为jQuery对象，这些对象继承了jQuery原型上定义的所有方法。

- jQuery将大量DOM操作定义成了方法（prototype上定义的函数），大大简化了DOM操作。

- JQuery 与 $ 符

  $是jQuery的别名（为了方便使用）

## 第四节 JQuery的缺点

### 1. 能向后兼容

每一个新版本不能兼容早期的版本。举例来说，有些新版本不再支持某些selector，新版jQuery却没有保留对它们的支持，而只是简单的将其移除。这可能会影响到开发者已经编写好的代码或插件。

### 2. 插件兼容性

与上一点类似，当新版jQuery推出后，如果开发者想升级的话，要看插件作者是否支持。通常情况下，在最新版jQuery版本下，现有插件可能无法正常使用。开发者使用的插件越多，这种情况发生的几率也越高。我有一次为了升级到jQuery 1.3，不得不自己动手修改了一个第三方插件。 

### 3. 多个插件冲突

在同一页面上使用多个插件时，很容易碰到冲突现象，尤其是这些插件依赖相同事件或selector时最为明显。这虽然不是jQuery自身的问题，但却又确实是一个难于调试和解决的问题。 

## 第五节 版本进化

- 2006年08月 jQuery 1.0
- 2007年01月 jQuery 1.1
- 2007年09月 jQuery 1.2
- 2009年01月 jQuery 1.3
- 2010年01月 jQuery 1.4
- 2011年01月 jQuery 1.5
- 2011年05月 jQuery 1.6
- 2011年11月 jQuery 1.7
- 2012年08月 jQuery 1.8
- 2013年01月 jQuery 1.9
- 2013年04月 jQuery 2.0
- 2016年07月 jQuery 3.0
- 2.0、3.0版不再支持IE 6/7/8，相较1.x版，代码小了12%，代码运行效率更高！




# 第二章选择器

## 第一节 基本

* id选择器 

```
$('#box')
```

* 标签选择器

```
$('div')
```

* class选择器

```
$('.box')
```

* 多个选择，用 “ , ”  分开

```
$('div,p,button')
```

* \* 代表所有标签

## 第二节 层级选择器

```js
//匹配所有后代元素
$('div span')

//匹配直接子元素
$('div>span')

//$("prev + next")
//匹配所有紧接在 prev 元素后的 next 元素
$("label + input")

//匹配 prev 元素的所有同辈 siblings 元素
$("form ~ input")
```


## 第三节 基本（增强）

* :first

获取**第一个**元素

* :last

获取**最后一个**元素

* :not

去除所有与给定选择器匹配的元素

* :even

匹配所有索引值为**偶数**的元素，从 0 开始计数

* :odd

匹配所有索引值为**奇数**的元素，从 0 开始计数

* :eq

匹配一个给定**索引值**的元素

* :gt

匹配所有**大于**给定索引值的元素

* :lt

匹配所有**小于**给定索引值的元素

## 第四节 内容、可见性、属性选择器

### 1. 内容

* :contains(text) 匹配包含给定文本的元素


* :empty 匹配所有不包含子元素或者文本的空元素


* :has(selector) 匹配含有选择器所匹配的元素的元素


* :parent 匹配含有子元素或者文本的元素

### 2. 可见性

* :hidden匹配所有**不可见**元素，或者type为hidden的元素


* :visible匹配所有的**可见**元素

### 3. 属性

* [attribute] 匹配包含给定属性的元素


* [attribute=value]匹配给定的属性是**某个特定值**的元素


* [attribute!=value]匹配给定的属性**不是某个特定值**的元素


* [attribute^=value] 匹配给定的属性是以**某些值开始**的元素

* [attribute$=value] 配给定的属性是以**某些值结尾**的元素


* [attribute*=value] 匹配给定的属性是以**包含某些值**的元素

## 第五节 子元素、表单、表单对象属性选择器

### 1. 子元素

* :first-child    匹配第一个子元素


* :last-child    匹配最后一个子元素


* :first-of-type    选择所有相同的元素名称的第一个兄弟元素


* :last-of-type    选择所有相同的元素名称的最后一个兄弟元素


* :nth-child    匹配其父元素下的第N个子或奇偶元素


* :nth-last-child()    选择所有他们父元素的第n个子元素。计数从最后一个元素开始到第一个


* :nth-last-of-type()    选择的所有他们的父级元素的第n个子元素，计数从最后一个元素到第一个
* :nth-of-type()     选择同属于一个父元素之下，并且标签名相同的子元素中的第n个
* :only-child     如果某个元素是父元素中唯一的子元素，那将会被匹配


* :only-of-type     选择所有没有兄弟元素，且具有相同的元素名称的元素。

### 2. 表单

* :input     匹配所有 input, textarea, select 和 button 元素


* :text     匹配所有的单行文本框


* :password     匹配所有密码框


* :radio    匹配所有单选按钮


* :checkbox    匹配所有复选框


* :submit    匹配所有提交按钮


* :image    匹配所有图像域


* :reset    匹配所有重置按钮


* :button    匹配所有按钮


* :file    匹配所有文件域


* :hidden    匹配所有隐藏域

### 3. 表单对象属性

* :enabled    匹配所有**可用**元素


* :disabled     匹配所有**禁用**元素


* :checked     匹配所有选中的**被选中元素**(复选框、单选框等，不包括select中的option)


* :selected    匹配所有选中的option元素（select元素用）


# 第三章 筛选

## 第一节 过滤

* eq()    获取第N个元素


* first()    获取第一个元素


* last()    获取最后一个元素


* hasClass()    检查当前的元素是否含有某个特定的类（如果有，则返回true）


* filter()    筛选出与指定表达式匹配的元素集合
* is()     匹配元素集合，如果其中至少有一个元素符合这个给定的表达式就返回true。
* has()    保留包含特定后代的元素，去掉那些不含有指定后代的元素


* not()    删除与指定表达式匹配的元素


* slice(start,end)    选取一个匹配的子集

## 第二节 查找

* children()    取得一个包含匹配的元素集合中每一个元素的所有子元素的元素集合。


* closest()    从元素本身开始，逐级向上级元素匹配，并返回最先匹配的元素


* find()     搜索所有与指定表达式匹配的元素


* next()     取得一个包含匹配的元素集合中每一个元素紧邻的后面同辈元素的元素集合


* nextall()     查找当前元素之后所有的同辈元素


* nextUntil()     查找当前元素之后所有的同辈元素，直到遇到匹配的那个元素为止


* offsetParent()     返回第一个匹配元素用于定位的父节点


* parent()     取得一个包含着所有匹配元素的唯一父元素的元素集合


* parents()     取得一个包含着所有匹配元素的祖先元素的元素集合（不包含根元素）。可以通过一个可选的表达式进行筛选。


* parentsUntil()     查找当前元素的所有的父辈元素，直到遇到匹配的那个元素为止


* prev()     取得一个包含匹配的元素集合中每一个元素紧邻的前一个同辈元素的元素集合


* prevall()     查找当前元素之前所有的同辈元素


* prevUntil()     查找当前元素之前所有的同辈元素，直到遇到匹配的那个元素为止


* siblings()    取得一个包含匹配的元素集合中每一个元素的兄弟元素集合

## 第三节 串联

* add()    把与表达式匹配的元素添加到jQuery对象中


* end()    回到最近的一个"破坏性"操作之前。即，将匹配的元素列表变为前一次的状态。

# 第四章 文档处理

## 第一节 内部、外部插入

### 1. 内部插入

* append()     向每个匹配的元素内部追加内容


* appendTo()     把所有匹配的元素追加到另一个指定的元素元素集合中


* prepend()     向每个匹配的元素内部前置内容


* prependTo()     把所有匹配的元素前置到另一个、指定的元素元素集合中

### 2. 外部插入

* after()     在每个匹配的元素之后插入内容


* before()     在每个匹配的元素之前插入内容


* insertAfter()     把所有匹配的元素插入到另一个、指定的元素元素集合的后面


* insertBefore()     把所有匹配的元素插入到另一个、指定的元素元素集合的前面

## 第二节 包裹 替换 删除 克隆

### 3. 包裹

* wrap()     把所有匹配的元素用其他元素的结构化标记包裹起来


* unwrap()     这个方法将移出元素的父元素。这能快速取消 .wrap()方法的效果


* wrapAll()     将所有匹配的元素用单个元素包裹起来


* wrapInner()     将每一个匹配的元素的子内容(包括文本节点)用一个HTML结构包裹起来

### 4. 替换

* replaceWith()     将所有匹配的元素替换成指定的HTML或DOM元素


* replaceAll()     用匹配的元素替换掉所有 selector匹配到的元素

### 5. 删除

* empty()     删除匹配的元素集合中所有的子节点


* remove()     从DOM中删除所有匹配的元素

### 6. 克隆

* clone()     克隆匹配的DOM元素并且选中这些克隆的副本

# 第五章 jQuery 核心

## 第一节 jQuery 对象访问
- length     获取的对象集合的长度


- each()     遍历对象中的每一个元素

* size()     获取的对象集合中元素的个数（这个是方法，length是属性）


* get()     取得其中一个匹配的元素（返回原生对象）


* index()    搜索匹配的元素，在本父级内同辈元素的索引，从0开始计数。

## 第二节 插件机制  数据缓存

* $.extend(object)     扩展jQuery对象本身


* $.fn    jQuery对象原型,可以为jQuery扩展方法

```javascript
//为jQuery原型增加新方法
$.fn.play=function(){
  	return this.each(function(){
      //do something...     
    })  
}
```

- $.fn.extend(object) 
  - 扩展 jQuery 元素集来提供新的方法（通常用来制作插件）。

```javascript
//为jQuery原型增加一组新方法（使用extend，合并对象）
$.fn.extend({
    run1:function(){
    	return this.each(function(){
      		//do something...
    	}) 
	},
  	run2:function(){
		retrun this.each(function(){//do something...
        })
  	}
})
```

## 第三节 属性

### 1. 属性 数据缓存

* attr()
  * 获取匹配的元素集合中的第一个元素的属性的值 或 设置每一个匹配元素的一个或多个属性
  * 若要检索和更改DOM属性,比如元素的checked, selected, 或 disabled状态，请使用prop()方法
* removeAttr()    从每一个匹配的元素中删除一个属性


* prop()    获取匹配的元素集中第一个元素的属性（property）值或设置每一个匹配元素的一个或多个属性


* removeProp()    用来删除由.prop()方法设置的属性集


* data()     在元素上存放数据,返回jQuery对象


* removeData()    在元素上移除存放的数据

###  2. CSS类

* addClass()    为每个匹配的元素添加指定的类名（多个类名用空格分开）


* removeClass()    从所有匹配的元素中删除全部或者指定的类（参数为空，删除元素所有类）


* toggleClass()    如果存在（不存在）就删除（添加）一个类。

### 3. HTML代码/文本/值

>  所有方法，带有参数为赋值，不带参数为读取值。

* html()    取得第一个匹配元素的html内容


* text()    取得所有匹配元素的文本内容


* val()    获得匹配表单元素的当前值

## 第四节 CSS

### 1. css

> 所有方法，带有参数为赋值，不带参数为读取值。

* css()    访问匹配元素的样式属性



### 2. 位置

* offset()     获取匹配元素在当前视口的相对偏移


* position()     获取匹配元素相对父元素的偏移


* scrollTop()     获取匹配元素相对滚动条顶部的偏移


* scrollLeft()     获取匹配元素相对滚动条左侧的偏移

### 3. 尺寸

* height()     取得匹配元素当前计算的高度值（px）


* width()     取得第一个匹配元素当前计算的宽度值（px）


* innerHeight()    获取第一个匹配元素内部区域高度（包括padding、不包括border）


* innerWidth()     获取第一个匹配元素内部区域宽度（包括padding、不包括border）


* outerHeight()     获取第一个匹配元素外部高度（默认包括padding和border）


* outerWidth()     获取第一个匹配元素外部宽度（默认包括padding和border）

# 第六章 事件

## 第一节 页面载入

* ready(fn) 当DOM载入就绪可以查询及操纵时绑定一个要执行的函数

```javascript
$(document).ready(function(){
   
})

//简写方式
$(function(){
    
})
```

## 第二节事件处理 

* on()    在选择元素上绑定一个或多个事件的事件处理函数

```javascript
$("#box").on("click",function(){
    /**/
})
```

* off()    在选择元素上移除一个或多个事件的事件处理函数

```javascript
$("#box").off("click,mousemove");
```

* one()    为每一个匹配元素绑定一个一次性的事件处理函数


* trigger()     在每一个匹配的元素上触发某类事件

```javascript
$("form:first").trigger("submit")
```

## 第三节 事件委派 

```javascript
//delegate() 
//指定的元素（属于被选元素的子元素）添加一个或多个事件处理程序，并规定当这些事件发生时运行的函数。

//undelegate() 
//删除由 delegate() 方法添加的一个或多个事件处理程序。
```

## 第四节 事件切换

* hover()     一个模仿悬停事件（鼠标over及out）的方法。

## 第五节 事件

* blur()        元素失去焦点时


* change()    元素的值发生改变时


* click()       单击元素时


* dblclick()     双击元素时


* focus()     元素获得焦点时


* keydown()    键盘或按钮被按下时


* keypress()    键盘或按钮被按下时


* keyup()    键盘或按钮被松开时，它发生在当前获得焦点的元素上


* mousedown()    鼠标指针移动到元素上方，并按下鼠标按键时


* mouseenter()    鼠标指针穿过元素时，该事件大多数时候会与mouseleave 事件一起使用


* mouseleave()    当鼠标指针离开元素时


* mousemove()    鼠标指针在指定的元素中移动时


* mouseover()    鼠标指针位于元素上方时


* mouseout()    鼠标指针从元素上移开时


* mouseup()    在元素上放松鼠标按钮时


* resize()    调整浏览器窗口的大小时


* scroll()    用户滚动指定的元素时


* submit()    当提交表单时

## 第六节 事件对象

> 适用的事件类型主要有键盘事件：keypress、keydown、keyup，以及鼠标事件：mouseup、mousedown。

* ev.pageX    鼠标相对于文档的左边缘的位置


* ev.pageY    鼠标相对于文档的上边缘的位置


* ev.stopPropagation()    防止事件冒泡到DOM树上，也就是不触发的任何前辈元素上的事件处理函数


* ev.preventDefault()    阻止默认事件行为的触发


* ev.target    最初触发事件的DOM元素


* ev.which     针对键盘和鼠标事件，这个属性能确定你到底按的是哪个键或按钮

# 第七章 效果

## 第一节 基本 滑动 淡出淡入

* show()    显示元素


* hide()    隐藏元素


* slidDown()    向下滑动显示


* slideUp()     向上滑动收起隐藏


* slideToggle()    交替滑动状态


* fadeIn()    淡入


* fadeOut()    淡出


* fadeTo()    动画到指定透明度


* fadeToggle()    交替淡出、淡入状态

## 第二节 自定义动画

* animate()    自定义动画


* stop()    停止所有在指定元素上正在运行的动画


* delay()    设置一个延时来推迟执行队列中之后的项目


* finish()    停止当前正在运行的动画，删除所有排队的动画，并完成匹配元素所有的动画

# 第八章 AJAX

* $.ajax()
* jQuery 底层 AJAX 实现。简单易用的高层实现见 $.get, $.post 等。$.ajax() 返回其创建的 XMLHttpRequest 对象。大多数情况下你无需直接操作该函数，除非你需要操作不常用的选项，以获得更多的灵活性。
* $.get()    通过远程 HTTP GET 请求载入信息


* $.getJSON()    通过 HTTP GET 请求载入 JSON 数据（如果返回的JSON有误，不会有错误提示）


* $.post()    通过远程 HTTP POST 请求载入信息

# 第九章 工具

* $.each()    通用例遍方法，可用于例遍对象和数组


* $.extend()    用一个或多个其他对象来扩展一个对象，返回被扩展的对象


* $.type(obj)    检测obj的数据类型


* $.isArray(obj)    测试对象是否为数组


* $.trim(str)    去掉字符串起始和结尾的空格


* $.inArray()    确定第一个参数在数组中的位置，从0开始计数(如果没有找到则返回 -1 )


* $.unique(array)    删除数组中重复元素。只处理删除DOM元素数组，而不能处理字符串或者数字数组


* $.merge(first,second)    合并两个数组



