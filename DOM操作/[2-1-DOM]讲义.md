# 第一章 BOM

- BOM  (browser object model) 代表浏览器对象模型

> 我们学习js语言，是要操作浏览器中的内容，要操作就要先找到要操作的东西，浏览器将js要操作的所有东西打包成一个对象，这个对象就是window对象，window对象里面封装了很多属性和方法，我们可以通过javascript语法，读取和操作这些属性，也可以调用window对象里面的方法，至于方法如何修改浏览器里面的内容，这些是底层原理，我们只需要学会怎么使用这些方法，不需要去弄懂这些方法是如何实现的

## 第一节 window对象

- window对象是浏览器提供给我们的
- window是javascript的顶级对象，也可以称作 全局对象，宿主对象
  - window对象不存在作用域的问题，任何地方，都可以读取和调用window对象的属性和方法
  - window对象的属性和方法在调用的时候，可以省略window
- 全局变量（变量，函数）存放在window中
- 在函数中，不用var声明的变量也是全局变量

```js
var obj = {
  name: 'zhangsan',
  say: function () {
    console.log('hello world!')
  }
}
console.log(obj.name);
obj.say();

var age = 18;
console.log( window.age );	//18
console.log( age );			//18
```

## 第二节 window 六大属性

- window对象里面封装了很多的属性和方法，其中经常用到的有六大属性

| history | location | navigator | screen | frames   | document |
| ------- | -------- | --------- | ------ | -------- | -------- |
| 历史记录    | 定位       | 导航        | 屏幕     | 框架集(已淘汰) | 文档（DOM）  |

1.  history 

```js
window.history.go(1) //前进（跳转）
window.history.go(-1) //后退（跳转）
window.history.forward() //前进
window.history.back() //后退
//浏览器中的前进后退按钮就是操作的这些方法
```

2. location

 ```js
window.location.href='http://www.baidu.com/'; //跳转地址

window.location.reload()  //刷新页面
//<a>标签可以跳转页面，js的location属性也可以跳转页面

//当以get方式在url中传递了请求参数时，可以利用location的search属性提取参数的值
console.log(location.search);
 ```

3. navigator    
 ```js
window.navigator.userAgent  
//可以读取用户的相关信息，如浏览器类型、版本、操作系统类型、内核（移动端）、浏览器引擎类型等
//如：判断是电脑登录网页或者手机登录网页
 ```
4. screen    
 ```js
window.screen.width    //返回当前屏幕宽度(分辨率值) 
window.screen.height    //返回当前屏幕高度(分辨率值) 
document.documentElement.clientWidth //浏览器窗口宽度（后面会讲解，用作对比）
 ```
5. frames 
- 该技术已经被淘汰
6. document  

- document是BOM属性中最重要的一个，后面详细讲解

## 第三节  BOM方法

> BOM提供了一系列的全局方法，方便随时调用。简而言之，这些方法都是浏览器提供的。

### 1. BOM弹框

- alert( )	警告弹框

- confirm( )    确认弹框

```js
if(confirm( "你确定吗？" )){
  	//点击确定之后执行的代码
}else{
  	//点击取消之后执行的代码
}
```

- prompt( )    提示输入弹框

```js
oBox.innerHTML = prompt( "请输入内容" );
```

- confirm和prompt因样式难看，已经被淘汰

### 2. BOM定时器

- setTimeout()    超时定时器

```js
setTimeout(function(){	//只执行一次
  	console.log("火星时代")
},1000)
//一秒之后控制台输出  火星时代
```

- setInterval( )    间隔定时器

```js
setInterval(function(){	//会无限执行，除非清除掉计时器
  	console.log("火星时代")
},1000)	//单位毫秒 1秒=1000毫秒
//每隔一秒控制台输出  火星时代
```

- 取消定时器

  - 计时器有一个返回值，代表当前的定时器，这个标识是唯一的。
  - 将返回值赋值给一个变量，使用清除计时器的方法即可

```js
//将计时器的返回值赋值给一个变量
var timer = setInterval(function(){},1000);
//计时器方法清除这个变量
clearInterval(timer);
//------------------------------------
var timer1 = setTimeout(function(){},1000);
clearTimeout(timer1);
```

- 间隔定时器的小套路

  - 1 将计时器返回值赋值给一个变量
  - 2 间隔计时器内部有一个计数器在变化
  - 3 执行计数器，当计数器达到程序的要求时，清除计时器

```js
var i=0;	//计数器
var timer = null;	//计时器的变量
timer = setInterval(function(){
  	console.log(i)		//代码块
    if(i==10){ clearInterval( timer) }		/判断条件，清除计时器
},1000);
```

## 第四节 BOM和DOM标准

- BOM 没有标准
- DOM w3c提供dom标准，css标准
- DOM标准和方法在一直扩充
- JavaScript ECMA提供标准

## 第五节 常用浏览器和内核

- 常用浏览器
  - 分别是IE、Firefox、Google Chrome、Safari、Opera。
- 浏览器内核

```html
1、IE浏览器内核：Trident内核，也是俗称的IE内核；
2、Chrome浏览器内核：统称为Chromium内核或Chrome内核，以前是Webkit内核，现在是Blink内核；
3、Firefox浏览器内核：Gecko内核，俗称Firefox内核；
4、Safari浏览器内核：Webkit内核；
5、Opera浏览器内核：最初是自己的Presto内核，后来是Webkit，现在是Blink内核；
6、360浏览器、猎豹浏览器内核：IE+Chrome双内核；
7、搜狗、遨游、QQ浏览器内核：Trident（兼容模式）+Webkit（高速模式）；
8、百度浏览器、世界之窗内核：IE内核；
9、2345浏览器内核：以前是IE内核，现在也是IE+Chrome双内核；
```



# 第二章 获取DOM对象

## 第一节 DOM

- DOM  (document object model 文档对象模型)
- 每个载入浏览器的 HTML 文档都会成为 Document 对象。
- Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问（读取和赋值）。

## 第二节 获取DOM对象得方法

> 页面交互的核心就是操作DOM元素，其中，第一步就是要找到要操作的DOM对象

### 1. getElementById( )

- 通过id获取DOM对象（唯一对象）

- 以函数返回值的形式返回找到的对象

- 如果没有找到，则返回null

  ```js
  var myBox = document.getElementById('box');
  //找到的元素是唯一的对象
  ```

### 2. getElementsByTagName( )

- 通过标签获取DOM对象（对象集合）
- 以函数返回值的形式返回找到的对象集合。
- 如果没有找到任何元素，返回一个空对象集合，转化成布尔值为true

```js
//在文档中找到标签名是div的所有标签
var divList = document.getElementsByTagName('div');
//可以在document下面直接 查找
```

```js
var myBox = myBox.getElementById('box');
//在myBox里面，找到标签名是div的所有标签
var divList = document.getElementsByTagName('div');
//也可以在特定的元素下面查找，查找的范围不一样
```

### 3. getElementsByClassName( )

- 通过页面中标签的class属性值获取DOM对象（对象集合）
- 以函数返回值的形式返回找到的对象集合。
- 如果没有找到任何元素，返回一个空对象集合，转化成布尔值为true

```js
//在文档中，找到所有class名为sub_nav的标签
var divList = document.getElementsByClassName('sub_nav');
```

- 通过getElementsByTagName和getElementsByClassName找到的事一个对象集合，类似于一个数组，包含着所有查找到的对象。
- 即使只找到了一个对象，也是对象集合。
- 对象集合跟数组类似，可以通过下标查找集合中的对象，也有length属性
- 对象集合的length是只读的，不能修改

```js
//数组的长度可以修改
var arr = ["火","星","时","代"];
arr.length = 2;
console.log(arr.length) // 2
console.log(arr) // ["火","星"]
```

```js
<div>1</div>  <div>1</div>  <div>1</div>  <div>1</div>  <div>1</div>
var divList = document.getElementsByTagName('div');	//对象集合
console.log(divList.length)	//5
divList.length = 3;	//对象集合的长度不能修改
console.log(divList.length)	//5
```

- 想要操作对象集合中的对象，要在对象集合后面加索引值才能找到具体的对象

```js
<div>1</div>  <div>1</div>  <div>1</div>  <div>1</div>  <div>1</div>
var divList = document.getElementsByTagName('div');	//对象集合
divList[1].style.background = "red";//第二个div背景变成红色
```

### 4. document.querySelector(‘ ’)

- 通过class选择器，查找单个对象

### 5. document.querySelectorAll(' ')

- 通过class选择器，查找对个元素，返回一个对象集合

## 第三节 遍历对象集合

- for循环：
  - 使用for循环可以遍历对象集合中所有的对象

```js
var divList = document.getElementsByClassName('sub_nav');
for(var i=0; i<divList.length; i++){	//语法三条语句，第三条不加“;”号
	divListp[i].style.background = 'red';
}
```

## 第四节 节点方式找对象

### 1. DOM树

- DOM结构就象树一样，从文档根---document，逐步分支展开
- 每一个元素，都可以看作是树的一个分支节点
- 每一个元素（节点）之间都存在着如下的一些关系：
  - 根节点	 父节点      子节点		兄弟节点

DOM树![](images/bom02.jpg)

### 2. 查找节点

- 父节点  ---parentNode
- 第一级所有子节点 ---children
- 第一个子节点 ---firstElementChild
- 最后一个子节点 ---lastElementChild
- 前一个兄弟节点 ---previousElementSibling
- 后一个兄弟节点 ---nextElementSibling

# 第三章 操作DOM对象属性和内容

> 任何一个html标签都包括标签名、内容、属性，本章节讲解如何操作一个标签

## 第一节 操作html标签

### 1. 标签名tagName

- 读取标签名 tagName
- 读取出来的标签名字全部是大写英文字母

```html
<div>
	<span></span>  
</div>
var box = document.getElementsByTagName('div')[0];
var text = document.getElementsByTagName('span')[0];
console.log(box.tagName)// DIV
console.log(text.tagName)// SPAN
```

### 2. 标签内容 (innerHTML|innerText)

- 标签内容：innerHTML | innerText
- 读取内容：
  - obj.innerHTML
  - obj.innerText 
- 设置内容：
  - obj.innerHTML = "火星时代";
  - obj.innerText = "火星时代";
- innerHTML 和 innerText 的区别
  - 在设置标签内容的时候，innerHTML 能够将字符串中的标签名识别出来。而innerText 不会识别，只能当字符串使用
  - innerText 不识别html标签 非标准  去除空格和换行
  - innerHTML 识别html标签 W3C标准 保留空格和换行的

```js
oBox.innerHTML = "<h1>能识别出来h1标签</h1>";
oBox.innerText = "<h1>不能识别出来h1标签，双引号内部的字符串都会被当成字符串</h1>";
```

- innerHTML的坑
  - 在用字符串方法增加innerHTML 时，会覆盖原有内容，原有内容绑定的方法将消失

```js
oBox.innerHTML += "<p>火星时代</p>";//等价于下一行
oBox.innerHTML = oBox.innerHTML + "<p>火星时代</p>";//相当于从新复制
//oBox原有标签中的内容所绑定的方法，会失效
//原因 i+=1  ====>  i=i+1,被从新赋值了
```

### 3. html标签的属性

- 标签属性分类
  - html标签的属性叫做attribute 分为三类
    - 全局属性   id class style title等，每个标签都有这些属性
    - 自有属性   有些标签有自己的属性，如：<a>href    <input> disabled
    - 自定义属性  data-    用户自己定义的属性，如data-index。多用于记录数据

```html
<div id="box" class="item" title="标题" data-index="1"></div>
<!-- div是标签名 id class title data-index 都是标签的属性 -->
```



- 操作HTML标签的属性attribute
  - 读取标签属性  var attr = obj.getAttribute('name')
  - 设置标签的属性 obj.setAttribute("name","value")
  - 判断是否有某个属性 var boo =  obj.hasAttribute("name")
  - 删除属性  obj.removeAttribute("name")
  - 有些属性用attribute操作不方便
    - disabled  checked   selected  readonly  使用对象的.语法

## 第二节 操作DOM对象

### 1. 对象的特性 property

- 操作一个对象，就要先找到这个对象，这个对象在初始化时，把html标签的全局属性和自有属性设置为对象的特性,还有很多其他特性。标签上面的自定义属性， 不会被设置成对象的特性

```js
var myBox = document.getElementById('box');
/*
myBox = {
  id:"myBox",
  className:"",
  title:"",
}
*/
```

- 读取对象的属性
  - 使用 . 语法读取对象的属性
  - 使用 [ ] 语法读取对象的属性，[]符号中添加的属性名是一个字符串

```js
console.log( myBox.id )
console.log( myBox["id"] )	//中括号加""
```

- 设置对象的属性
  - 使用 . 语法设置对象的属性
  - 使用 [ ] 语法设置对象的属性

```js
 myBox.className = "header";
 myBox['className'] = "header";
```

- 通过定义对象的属性，我们可以做很多事情，比如记录一些数据，索引值等等

```js
var aLi = document.getElementsByTagName('li');
for(var i=0; i<aLi.length; i++){
  aLi[i].index = i;		//给每一个li设置一个属性index
};
console.log(aLi[2].index); //2
```

### 2. 特定的特性

- href属性:   如css引用路径

```js
document.getElementsByTagName('link')[0].href = 'base.css'
```

- src属性:  如图片引用的路径

```js
document.getElementById('bigImg').src = 'images/pic01.jpg'
```

- className
  - 可以读取和修改某个对象的类名

```js
//读取oBox的类名
console.log(oBox.className);
//增加类名 注意引号中要加一个空格
oBox.className += ' ac';
```

- classList 操作类名的新方法
  - 删除某个类名 div.classList.remove("ac");
  - 添加某个类名 div.classList.add("ac");
  - 切换某个类名 div.classList.toggle("ac");
  - 确定元素中是否包含某个类名返回布尔值 div.classList.contains("ac")
- 设置style属性

```js
oBox.style.backgroundColor = 'red';
//oBox.stylebackground-color 
//background-color 中的“-”在js语法中是减号，因此改成backgroundColor
```

- 读取style样式   只能读取行内样式，因此不建议用这个。 

```js
var a = obj.style.width;		
//这样只能读取出来行内样式，读取不了css样式表，而我们写样式，都写在样式表里面，不会写在行内
```

- getComputedStyle("元素", "伪类")  可以获取当前元素所有最终使用的CSS属性值
  - 读取出来的数据是字符串
  - 如果没有修改元素的属性，读取出来的就是css样式表中的属性值，如果修改过样式，则读取出来的是最终的属性值

```js
var style = getComputedStyle(oBox, null)	//读取oBox的样式
console.log(style.width) 	//355px   读取出来的是字符串
//如果想读取该元素的为元素的属性，如下
var style = getComputedStyle(oBox, ':after')
console.log(style.width) 	//35px   读取出来的是字符串
```

- dom元素尺寸
  - offset    偏移		（当元素的属性display为none 的情况下读取不出来）
    - offsetWidth  宽度(width+padding+border)
    - offsetHeight 高度(height+padding+border)
    - offsetLeft   左    计算到有定位属性（position）的父级边缘
    - offsetTop    上    计算到有定位属性（position）的父级
    - offsetParent 父级  有定位属性（position）的父级，如果其父元素一直没有定位属性，则返回body
    - 只能读取，不能赋值 赋值用obj.style.width
  - client-     客户端
    - clientWidth ---获取对象可见内容的宽度，不包括滚动条，不包括边框；
    - clientHeight --- 获取对象可见内容的高度，不包括滚动条，不包括边框；

# 第四章 操作DOM间的关系

> 之前我们都是在操作页面中已有的dom元素
>
> 通过js可以对dom元素进行创建、插入、替换等操作。此操作是交互操作的重要部分。

## 第一节创建DOM对象

### 1. document.createElement

- 语法： document.createElement( 'div' )
  - 一个参数，要创建的标签的名字
  - 一定是document.createElement，固定语法，不能该表
  - 创建的元素，是在内存级别 ，我们看不到，如果要放到页面中，要使用js语法操作
  - 创建的一个元素，多次插入页面中，也还是一个元素，而不是页面中有很多相同的元素

### 2. 克隆

- 语法：obj.cloneNode(true) ;
  - 克隆出来的对象，也是在内存级别中

```js
var new_obj = obj.cloneNode(true);
//true:包含子元素，false只复制当前元素，不复制子元素
```

- 克隆出来的对象是新元素

## 第二节 插入节点

### 1. appendChild

- box.appendChild( elm )    把elm插入到box内（尾部）

### 2. insertBefore

- box.insertBefore( a,b)   box盒子内，把a元素插入b元素之前

## 第三节 替换元素

- box.replaceChild( a,  b)  box盒子内，用a元素替换掉b元素

## 第四节 删除元素

- box.removeChild(a )  把box内的a元素删除

# 第五章 事件

> 用户在浏览网页时，会产生各种各样的交互事件，比如鼠标点击事件 、敲击键盘事件等。这样的事件行为都是通过操作DOM上的一类特殊属性来实现的--------DOM事件，不同的DOM事件会有不同的触发条件和交互效果。有些DOM事件是所有DOM对象都有的，而有些DOM事件，是部分DOM对象独有的。

## 第一节 什么是事件

- 不同标签，有相同的事件，也有不同的事件
  - 很多标签都有onclick事件，select有onchange事件(内容发生改变)，input有onblur事件(失去焦点)
  - console.dir(oBox),能看到这个对象有很多事件，在没有定义的时候，这些事件的值都是空
- 当 事件 发生的时候，要做什么事（函数）---------- 为了做一件事
  - oBox.onclick = function(){}

## 第二节 事件绑定

### 1. 赋值方式

- 通过为DOM对象的事件属性赋值一个函数的方式，为DOM元素绑定事件，当该对象的事件被触发时，调用这个函数，例如:

```js
var oDiv=document.getElementById('box');
oDiv.onclick=function(){  //为oDiv绑定鼠标的点击(onclick)事件,当点击这个div时,这个函数将会运行
	alert('hello world'); //系统提示框
};
```

### 2. 事件监听

- addEventListener('type',fn,false )    增加事件监听 (可以为一个元素，同时绑定多个事件)
  - type为触发函数的事件类型，fn为事件触发时执行的函数，false为事件冒泡阶段触发，如果第三个参数改成true，则为捕获阶段触发
  - 绑定的事件不加on       onclick==》click      onmouseenter==> mouseenter
  - 时间监听方法一个事件，可以绑定不同的函数，在该事件触发时，绑定在该事件下的所有函数都会触发

```js
oBox.addEventlistener('click',function(){
  	alert("hxsd");
},false);
oBox.addEventlistener('click',function(){
  	alert(222);
},false);
//点击oBox时候，会弹两次弹框
//-----------------------------
oBox1.onclick = function(){
  alert(111)
};
oBox1.onclick = function(){//从新赋值
  alert(222)	
}
//点击时候只会弹出一个222
```

- removeEventListener('type',fn,false )    删除事件监听

## 第三节 事件的触发（调用）

- 谁调用事件处理函数？？---函数只有调用才能执行;

```js
document.onclick = run; //点击触发函数

function run(){
  console.log("函数运行了")
}；
run(); //直接调用函数
```

## 第四节 事件分类

### 1. window事件

- onload    加载（某个页面或图像被完成）

```js
window.onload =function(){
  //页面加载完成时候，再运行函数，多用于script标签写在body前面的时候
}
```

- onresize    窗口或框架被调整尺寸（调整浏览器大小）
- onscroll    滚动条事件
  - 页面滚动条高度：页面滚动出浏览器的高度。

```js
//读取滚动条的高度。浏览器兼容问题
var scrolltop = document.documentElement.scrollTop || document.body.scrollTop;

//赋值
document.documentElement.scrollTop = 100
```

### 2. 鼠标事件

- onclick    鼠标点击
- ondblclick    鼠标双击
- onmousedown    鼠标按键按下
- onmouseup    鼠标按键被松开
- onmouseenter    鼠标进入某元素  
- onmouseleave    鼠标离开某元素
- onmousemove    鼠标移动
- oncontextmenu    右键菜单 （有的教科书叫上下文菜单）
- onmousewheel    谷歌浏览器鼠标滚轮事件  
  - ev.wheelDelta   判断向上滚动或者向下滚动

```js
oBox.onmousewheel = function(ev){
  console.log(ev.wheelDelta)
}
//向上滚动的时候，得到的数值是150
//向下滚动的时候，得到的数值是-150
//可以根据数值的正负判断鼠标滚轮的滚动方向
```

- DOMMouseScroll    火狐浏览器鼠标滚轮事件
  - ev.detail    判断向上滚动或者向下滚动

```js
oBox.addEventListener('DOMMouseScroll',function(ev){
  console.log(ev.detail)
},false)
//向上滚动的时候，得到的数值是-3
//向下滚动的时候，得到的数值是3
//可以根据数值的正负判断鼠标滚轮的滚动方向
```

- 滚轮事件兼容写法

```js
function mouseWheel(obj,fn){//obj：在某个对象是滚动 fn：回调函数，做什么事情
    if(window.navigator.userAgent.indexOf("Firefox") !=-1){//火狐
      obj.addEventListener('DOMMouseScroll',wheelFn,false)
    }else{
      obj.onmousewheel = wheelFn;//谷歌
    }
    function wheelFn(ev){//判断滚动方向，返回布尔值   向上返回false ，向下返回true
      var direct = ev.wheelDelta ?ev.wheelDelta<0 : ev.detail>0; //120<0 或 -3>0
      fn&&fn(direct);//布尔值，实参
      ev.preventDefault();
    }
}
```

### 3. 表单事件

- onblur    元素失去焦点
- onfocus     元素获得焦点
  - input输入框
  - input外边框css样式：

```css
input{ outline: none; border:1px #666 solid}
```

- onchange    内容改变时触发
  - js读取select的值就是选择框显示的option的value
  - select选择时会触发

```html
<select>
  	<option value="1">A</option>
  	<option value="2" selected>B</option>
  	<option value="3">C</option>
</select>
<!-- 此时select默认选中的是第二个option，这个select的值也是2 -->
```

- 读取和设置表单的值  value

```js
var oInput = document.getElementsByTagName('input')[0];
console.log( oInput.value );//读取value值
oInput.value = "火星时代";	//设置value值
```

- isNaN(a) 判断a是不是NaN
  - 如果a是数字，返回false
  - a不是数字，返回true

### 4. 键盘事件

- 键盘事件
  - onkeydown    按键按下
  - onkeypress 按键按下的时候触发  不能识别功能键 比如 ctrl shift 左右箭头等
  - onkeyup    按键释放
- 三个事件的执行顺序  keydown -- keypress -- keyup

## 第五节 事件对象（Event）

> 鼠标在在页面上滑动，肯定是鼠标的onmousemve事件，如何得到鼠标的坐标值呢？document上按键，能触发事件，怎么知道我按的是哪一个按键？
>
> 一定会有个地方存储着这些值，方便我们去读取。获取事件数据，不同的事件会有不同数据

### 1. 什么是事件对象

- 绑定在事件上的匿名函数，只可以有一个参数，这个参数就代表事件对象
- 事件对象代表事件的状态，比如事件在其中发生的元素、键盘按键的状态、鼠标的位置、鼠标按钮的状态。
- 事件对象只有有了事件才会存在，它是系统给我们自动创建的，不需要我们传递参数
- 这个事件对象我们可以自己命名 比如 event 、 evt、 e

```js
oBox.onclick = function(ev){	//	参数名：ev || event || e 或者任意名字都可以
  //ev就是事件对象
  console.log( ev.clientX);	//鼠标距离浏览器窗口的横坐标值
  console.log( ev.clientY);	//纵坐标
  //鼠标点击事件的 事件对象是鼠标事件对象，这个对象里面又存放了很多跟鼠标相关的属性
}
```

### 2. 事件对象的相关属性

- 鼠标:
  - 鼠标相关的事件 函数中的事件对象就是鼠标对象，里面存放的属性和方法都跟键盘有关
  - ev.button    鼠标按钮 0：左键    1：中键       2：右键
  - client 鼠标在可视区的x和y坐标
    - ev.clientX  
    - ev.clientY  
  - page 鼠标在页面文档的x和y坐标     
  - screen 鼠标在电脑屏幕的x和y坐标
- 键盘:
  - 键盘相关的事件 函数中的事件对象就是键盘对象，里面存放的属性和方法都跟键盘有关
  - ev.keyCode键盘编号
  - ev.ctrlKey "Ctrl" 键按下 ev.ctrlKey==1
  - ev.altKey  "Alt" 键按下  ev.altKey==1
  - ev.shiftKey  "Shift"键按下 ev.shiftKey==1

## 第六节 事件流

### 1. 默认事件

- 很多的网页元素都会有默认的行为，比如说当你点击一下超链接a标签的时候，它会有一个跳转的行为；当你在网页上点鼠标右键时会出现一个右键菜单；这些行为，并不是通过绑定函数来实现的，这类行为被称为对象的默认行为
- 阻止默认行为：event.preventDefault()   （w3c规范）
- 点击a链接，默认事件是 跳转网页 ，可以阻止
- mousedown，默认事件是可以框选文字
- oncontextmenu，默认事件是

### 2. 事件流

> 在点击页面中某个元素的时候，先点到的元素，还是先点到的document？

- 事件捕获  （document  > body > ev.targrt）
  - 事件从最不精确的对象(document 对象)开始触发，然后到最精确(也可以在窗口级别捕获事件，不过必须由开发人员特别指定)。
- 事件目标     ev.targrt
- 事件冒泡   ( ev.targrt > body >document )
  - 事件按照从最特定的事件目标到最不特定的事件目标(document对象)的顺序触发。
  - 注意：触发子元素的事件时候，会把父元素相同的事件也触发了;
  - focus  blur  change  scroll  submit 没有冒泡
  - onclick 会冒泡 onmousedown onmouseup事件  要分别进行阻止
  - onkeypress 会冒泡 onkeydown onkeyup事件
- W3C定义事件流：同时支持两种事件模型：捕获型事件和冒泡型事件，但是，捕获型事件先发生。从document对象开始，到目标元素，回到document对象结束。
- 阻止事件冒泡  ev.stopPropagation()   （w3c规范）

### 3. 事件目标

- 事件目标  ev.targrt		
  - 鼠标真正作用在了什么元素上，那这个元素就是事件目标。事件目标通常和事件委派一起使用

### 4. 事件委派

- 把事件委托到父元素上，利用冒泡原理，当子元素点击时，由于冒泡原理，事件会冒泡到父元素上，父元素上面的事件就会触发执行。
- 通过判断事件的“目标元素”来触发父级上绑定的事件
  - ev.currentTarget真正绑定事件的元素

```js
oBox.onclick =function(ev){
  //ev.currentTarget =>oBox
}
```

- 作用
  - 不用分别为子元素绑定事件
  - 为未知元素绑定事件

# 第六章 移动端touth事件

## 一、事件名

- 移动端浏览器兼容性较好，我们不需要考虑以前 JS 的兼容性问题，可以放心的使用原生 JS 书写效果，但是移动端也有自己独特的地方。比如触屏事件 touch（也称触摸事件），Android和 IOS 都有。
- touch 对象代表一个触摸点。触摸点可能是一根手指，也可能是一根触摸笔。触屏事件可响应用户手指（或触控笔）对屏幕或者触控板操作。
- 常见的触屏事件如下：

| 事件        |                                              |
| ----------- | -------------------------------------------- |
| touchstart  | 当手指触摸屏幕的时候出发                     |
| touchmove   | 当手指在屏幕移动的时候                       |
| touchend    | 手指离开屏幕的时候触发                       |
| touchcancel | 当被迫中止滑动的时候触发（弹消息，来电等等） |

## 二、事件绑定方法

- 移动端使用事件监听的方式绑定事件

```js
window.onload = function(){
   var box = document.querySelector('.box');
   box.addEventListener('touchstart', function(ev){
    console.log(' start ');
    console.log(ev); //事件对象，每一个事件都有一个触摸事件对象
   })
}
```

## 三、事件对象

|    事件对象     |                                             |
| :-------------: | :-----------------------------------------: |
|    TouchList    |   触摸点的集合（一个手指就是一个触摸点）    |
| changedTouches  | 改变后的触摸点集合   每个事件都会记录触摸点 |
|  targetTouches  |  当前元素的触摸点集合  离开屏幕时无法记录   |
|     touches     |  页面上所有触摸点集合  离开屏幕时无法记录   |
| clientX clientY |           基于浏览器窗口（视口）            |
|   pageX pageY   |               基于页面(视口)                |
| screenX screenY |                  基于屏幕                   |

- 移动端的点击事件其实是一个开始触碰，和触碰离开构成的，但是移动端滑动事件，其实也是有开始触碰和触碰离开构成，只不过中间有一个移动事件。为了区分是点击事件，还是滑动事件，需要封装一个事件

```js
window.onload = function () {
      /*给dom绑定手势事件, 绑定完成之后要执行的操作(回调函数)*/
      var box = document.querySelector('.box');
      console.log(box);
 
      var bindSwipeEvent = function (dom, leftCallback, rightCallback) {
        /* 首先确定事件触发的条件 */
        var startX = 0,
            distance = 0,
            isMove = false;
        dom.addEventListener('touchstart', function (e) {
          startX = e.touches[0].clientX;
          // console.log(startX);
        })
        dom.addEventListener('touchmove', function (e) {
          isMove = true;
          var moveX = e.touches[0].clientX;
          console.log(moveX);
          distance = moveX - startX;
          console.log(distance);
        })
        dom.addEventListener('touchend', function (e) {
          if (isMove && Math.abs(distance) > 50) {
            if (distance > 0)
              //条件成立,如果当前对象dom传入了leftCallback 就使用回调函数调用该方法
              leftCallback && leftCallback.call(this, e);
            else
              rightCallback && rightCallback.call(this, e);
          }
          startX = 0;
          distance = 0;
          isMove = false;
        })
      }
      /* 调用 */
      bindSwipeEvent(box, function (e) {
        console.log(this);
        console.log('右滑');
      }, function (e) {
        console.log(this);
        console.log('左滑');
      })
    }
```

# 第七章 本地存储

## 第一节 本地存储特性

- 数据存储在用户浏览器中

- 设置、读取方便、甚至页面刷新不丢失数据

- 容量较大，sessionStorage约5M、localStorage约20M

- 只能存储字符串，可以将对象JSON.stringify() 编码后存储

## 第二节 window.sessionStorage

- 生命周期为关闭浏览器窗口

- 在同一个窗口(页面)下数据可以共享

- 以键值对的形式存储使用

- 存储数据：

```javascript
sessionStorage.setItem(key, value)
```

- 获取数据：

```javascript
sessionStorage.getItem(key)
```

- 删除数据：

```javascript
sessionStorage.removeItem(key)
```

- 清空数据：(所有都清除掉)

```javascript
sessionStorage.clear()
```

## 第三节 window.localStorage

- 声明周期永久生效，除非手动删除 否则关闭页面也会存在

- 可以多窗口（页面）共享（同一浏览器可以共享）

- 以键值对的形式存储使用

- 存储数据：

```javascript
localStorage.setItem(key, value)
```

- 获取数据：

```javascript
localStorage.getItem(key)
```

- 删除数据：

```javascript
localStorage.removeItem(key)
```

- 清空数据：(所有都清除掉)

```javascript
localStorage.clear()
```





