# 第一章 JavaScript基础知识

## 第一节 JavaScript简介

- JavaScript 是非常简单易学的计算机脚本语言。
- JavaScript主要用于实现用户与电脑、手机、iPad等多种设备的交互效果。
  - 交互效果：用户与浏览器的互动，如点击登录按钮弹出登录弹窗，点击一些按钮，改变页面中的内容，登录账户等等。

## 第二节 JavaScript 书写位置

> JavaScript的书写位置和CSS的书写位置一样，有三种书写位置
### 1. 外部JavaScript文件
- 将js语言写在JavaScript文件中，通过`<script>`标签引入到HTML网页中
- 在HTML5中，`<script>`标签已经不需要书写`type="text/javascript"`,因为html会默认执行此标准。
- 注意：写有`src`属性的`<script>`标签中不要写js语言，不会被浏览器解释执行。
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<script src="js/demo.js"></script>
	</head>
	<body>
	</body>
</html>
```

### 2. 将js写在页面中script标签中

- js文件可以写在页面中的`script`标签中。


- `script`标签可以写在head或者body标签中。
- script标签如果写在head标签中，如果出现网络延迟或其他问题，script标签不能顺利加载的情况下，那么HTML结构也不会加载，所以为了不影响结构加载，通常script标签写在body标签的尾部。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
      	<div></div>
      	<ul>
          	<li></li>
      	</ul>
      	<script>
      		alert("hello world")
      	</script>
	</body>
</html>
```

### 3. js文件写在HTML标签中

- 早期的JavaScript 事件通常会写在HTML中。
- 现在写代码，注重表现与结构分离，通常前端开发会将css写在css文件中，将JavaScript写在js文件中，所以现在很少将JavaScript标签写在HTML标签中。

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<body>
      	<div onclick="alert('hello world')"></div>
	</body>
</html>
```

## 第三节 JavaScript输出

### 1. 在页面中输出语句

- 使用`document.write()`可以在浏览器页面中输出内容，要显示的内容写在`()`内。

```javascript
document.write("你好，火星时代")
```

### 2.  在浏览器弹窗中输出语句

- 使用`alert()`可以在浏览器中弹出弹窗显示内容，要显示的内容写在`()`内。

```js
alert("hallo world");
```

### 3. 在浏览器控制台输入内容

- 浏览器控制台是专门给程序员调试代码使用的，打开浏览器，按`F12`键即可呼出控制台。

- 使用`console.log()`可以在浏览器控制台打印内容，要显示的内容写在`()`内。

```js
console.log("火星时代");
//在控制台的console选项卡内，可以看到打印出来的 火星时代
```

##  第四节 JavaScript注释

> 在编写JavaScript语言中，也有注释语法，和HTML和CSS一样，注释的内容，不会显示在页面中，也不会发挥作用，在我们调试代码或者写一些提示性语言时，可以使用JavaScript注释

### 1. 单行注释

- 如果只想注释一行文字，可以使用单行文字注释。
- 单行注释的语法： 在需要注释的内容前，加上`//`

```js
//我是需要注释的文字，不会执行，也不会在页面中显示
```

### 2. 多行注释

- 需要大量注释或者要注释一段内容的时候，使用多行注释。
- 多行注释的语法： 将需要注释的内容，放在`/* */`中间。

```js
/*需要多行注释的文字，可以放在这里
需要多行注释的文字，可以放在这里
需要多行注释的文字，可以放在这里*/
```

## 第五节 JavaScript 语法规范

- JavaScript语言区分大小写，忽略大小写可能导致程序错误。

```js
alert("hxsd");			//正确
ALERT("hxsd");			//错误
```

- JavaScript每行结束后，要使用`;`分隔，用于告诉浏览器语句结束了。

  > 很多同学在书写js语句的时候，会忽略大小写，因为js语句结束时，我们通常换行写写一行js，但是在项目开发完成后，代码通常会被压缩，此时换行就会被删除掉，那么没有`;`的语句，就没有分隔，都写在了一样，必然报错

- JavaScript符号，要区分中英文状态，写成中文符号会导致程序报错。

- JavaScript语言中关键字间要有空格，空格一方面是代码规范，另一方面可以使代码清晰可分辨。


```js
var age=18;		//格式正确
var age = 18;	//格式正确，代码清晰
varage=18;		//报错
```

# 第二章 数据和变量

> 生活中，我们会用不同的词语或者大篇的段落去描述不同的事物，比如形容一个人的姓名，年龄，是否结婚。姓名：张三， 年龄：22，是否结婚：是或者否， 爱好：唱歌，购物。
>
> 在JavaScript语言中，想要表示一个事物，也会用不同的数据去描述它，这些数据存放在内存中，使用变量来表示，下面我们来学习变量。

## 第一节 变量是什么

- JavaScript 中所有的数据，都存放在计算机的内存中，js表示这些数据的专有名词叫`变量`。
- 用于表示数据的词汇就是变量名，数据的值就是变量值。

```js
var hxsd = "火星时代实训基地。";
//此处hxsd就是变量名，而等号后面的，就是变量的值，即数据。
```

## 第二节 声明变量

### 1. 变量声明方法

- 使用关键字 `var` 声明变量，变量名字和关键字`var`中间要有空格。

```js
var userName;
```

- 声明变量就是在内存中开辟了一块空间，用于存放数据。
- 使用关键字var一次可以声明一个变量，也可以声明多个变量，使用`,`分隔。

```js
var userName;		//声明一个变量

var a,b,c;			//多个变量名之间使用，分隔
```

### 2.变量命名规范

- 变量名区分大小写，允许包含字母、数字、美元符号`$`和下划线`_`，但第一个字符不允许是数字，不允许包含空格和其他标点符号。
- 禁止使用JavaScript关键词、保留字全名。
- js关键字举例：boolean、 break、 for、 this等等。

## 第三节 变量赋值

### 1. 变量默认值

- 只声明了变量，这时候内存中就会有相对应的空间存放着这个变量，但是这个变量还没有赋值，JavaScript讲他的值默认修改为 `undefined`，代表声明了变量，但是变量还没有赋值。

```js
var zs;
console.log(zs);//undefined
```

### 2.  给变量赋值

- 变量用于存放数据，所以变量都应该有自己的值。
- 使用`=`号为变量赋值，值写在变量的右边。

```javascript
var zs;
zs = "zhangsan";

var age;
age = 18;
```

### 3. 声明变量并同时赋值

- 在声明变量的时候，可以同时给变量赋值，一气呵成。

```js
var zs = "zhangsan";
var age = 20;
console.log(zs)		
//浏览器控制台会显示 zhangsan
```

### 4. 修改变量的值

- 变量的值可以随意修改，修改起来也非常简单，只需要用`=`从新赋值即可。

```js
var name = "zhangsan";
name = "lisi";
console.log(name);  //lisi
```

# 第三章 数据类型

> js中有很多种数据类型，这些数据用来表示一种事物的不同属性，比如形容一个人，可以有名字，年龄，是否结婚，爱好等等。这些都可以用js的不同数据来实现。
>
> 姓名：张三（字符串）， 年龄：22（数字），是否结婚：是或者否（布尔值：true/false） 爱好：唱歌，购物（数组）
>
> ### js中的基本数据类型有8种，分别是 字符串 数字 布尔值 undefined null array object function

## 第一节 字符串 string

- 字符串用来表示一段文字
- 字符串要用`" "`或者`' '`包裹
- 注意：`''` 或 `""` 本身只是一种表示方式，不是字符串的一部分，因此：`"abc"` 只有`a` `b` `c` 这个三个字符。
- 注意，不管是单引号还是双引号，都要成对出现。

```js
var str = "hello world!";
var str = '你好 世界';
```

- 如果字符串内没有声明字符，这个字符串就是空字符串。
- 注意，字符串内即使有一个空格，也不是空字符串。

```js
var str1 = "";		//空字符串
var str2 = " "; 	//非空字符串
```

## 第二节 数字 number

- 数字相关的数据，都可以用数字类型的变量表示。
- js不区分整数和浮点数，统一用number表示，以下都是合法的number类型
- 数字可以是,正数，负数，整数，小数和科学计数法。

```js
var num1 = 20;
var num2 = 33.5;
var num3 = 125e5;      // 12500000
var num4 = -3;
```

- 数字类型的数据千万不要放在`""`内，因为那样就不是数字类型，而是字符串类型。

## 第三节 布尔值 boolean

- 布尔值用于表示真和假
- 布尔值类型的数据，只有两个值，true和false，代表真和假。
- 如天气是否下雨，下雨（true），不下雨（false）。

```js
var isRain = true;		//布尔值，true代表真
var flag = false;		//布尔值，false代表假
```

## 第四节 undefined

- 变量声明后，如果没有赋值，js会默认给变量赋值undefined。
- undefined是一种数据类型，它只有一个值，值也是undefined。

```js
var a;				//声明变量，但是没有赋值
var b = 10;
console.log(a);		//undefined
```

## 第五节 对象 object

- JavaScript对象是一种相对复杂的数据类型，和字符串数字等简单数据类型不同的地方在于，一个对象，可以表示很多数据。
- 对象是一种数据类型，它的数据结构表现形式有三种，分别是空对象（null），数组（array），对象（object）。

### 1. 空对象 null

- null值表示一个空对象指针，用来表示本来可以找到一些对象，但实际没有找到，所以用null来表示。

```js
var obj = null;		//obj是空值
```

### 2. 数组 array

- 数组是由多个数据组成的数据的集合体。
- 数组的语法格式是使用`[ ]`,包裹一组数据，每个数据之间用`,`分隔。

```js
var arr = ["HTML","CSS"，"JavaScript"];
//此处声明一个web的变量，值是数组类型，数组里面存放了三个数据
```

- 数组中每个数据，都可以是不同的数据类型。可以是：数字，字符串，布尔值，undefined，对象。
- js提供了很多方法，用于操作数组，后面的章节会详细讲解

### 3. 对象 object

- 对象和数组类似，可以存放很多数据，但是数据的格式和表现形式都不同。
- 对象的语法是数据使用`{}`包裹，内部使用属性名和属性值表示数据，语法如下。

```js
var zs = {
  	name:"张三",		//name是属性名，张三是属性值，属性名和属性值用:分隔，每条属性使用,分隔
  	age:18,
  	city:"北京"
}
```

## 第六节 函数 function

- JavaScript中函数是一种数据类型
- 函数就是若干代码语句的集合，方便重复使用。
- 定义好函数，函数不会立即执行，而是需要事件驱动（如点击鼠标触发函数）或者调用函数，函数才会执行。
- 声明一个函数，有赋值方式和字面量声明方式

```js
function run(){		//定义函数，字面量声明
  	console.log("调用函数，就可以执行这条语句");
}

run()				//调用函数
//------------------------------------------------
var foo = function(){	////定义函数，赋值方式
  	console.log("调用函数，就可以执行这条语句");	
}；
foo();		//调用函数
```

## 第七节 typeof 运算符

- 想要简写数据属于哪一种数据类型，js提供了typeof运算符，typeof会返回变量的数据类型。
- typeof 可以返回6种数据类型，分别是 string number boolean undefined object function

```js
var a = "hxsd";			
var b = 20;				
var c = true;			
var d;					
var e = null;			
var f = [1,2,3];
var g = {name:"zhangsan"};
var h = function(){};

typeof a;		//string
typeof b;		//number
typeof c;		//boolean
typeof d;		//undefined
typeof e;		//object
typeof f;		//object
typeof g;		//object
typeof h;		//function

```

# 第四章 运算

## 第一节 算术运算

> js提供了一些基础的运算符，此处我们讲解加减乘除和取余数运算符
>
> 生活中我们做数学运算，都是数字与数字之间做运算，js不光有数字运算，字符串，布尔值等都可以进行数学运算

### 1. 加法运算

- 加法运算符`+`
- 数字和数字之间做运算，将两个数字相加即可。
- 字符串和字符串做加法，就是把字符串拼接成一个字符串。

```js
var a = 10;
var b = 20;
var c = "abcd";
var d = "100";

console.log(a+b);		//数字与数字，返回30；
console.log(c+d);		//两个都是字符串类型，做字符串拼接，返回"abcd100"
```

### 2. 减法运算

- 加法运算符`-`
- 数字和数字之间做运算，将两个数字相减即可。
- 数字和字符串之间做加法，js会将字符串转换成数字，如果字符串不能转化成数字，则返回NaN。

```js
var a = 10;
var b = 20;
console.log(a-b)		//-10
```

### 3. 乘法运算

- 乘法运算符`*`
- 数字和数字之间做乘法，将两个数字相乘即可。

```js
var a = 10;
var b = 20;
console.log(a*b)		//200
```

### 4. 除法运算

-  除法运算符`/`
-  数字和数字之间做乘法，用后面的数字除以千年的数字即可。

```js
var a = 10;
var b = 20;
console.log(a/b)		//0.5
```

### 5. 取模运算（取余数）

- 取模运算符`%`
- 取模运算简答你的理解就是求余数

```js
var a = 9;
var b = 4;
console.log(9%4);		//1		9能去除2个4，余下的数字就是1
```

### 6. 运算符优先级

![](images/youxianji.png)	

## 第二节 隐式转换

> 上一节我们学习的加减乘除和取模运算，都是数字与数字之间的，js不光是数字类型可以做运算，字符串，布尔值都可以做运算

- 隐士转换的概念：在运算中，如果两个数据的数据类型不同，js会自动将某个数据转换成和另一个数据相同的数据类型，这种转换无需用户操作，所以称之为隐式转换。

### 1. 加法中的隐士转换

- 数字和布尔值做运算，布尔值true会转换成数字1，false会转换成数字0，然后再做加法。

```js
var a = 100;
var b = true;
var c = false;
console.log(a+b);		//101
console.loog(a+c);		//100
```

- 字符串和数字做加法，数字会隐式转换成字符串，两者做字符串拼接。

```js
var a = 100;
var b = "20";
console.log(a+b);		//"10020"
```

- 字符串和布尔值做加法，布尔值会转换成字符串。做字符串拼接。

```js
var a = "abc";
var b = true;
var c = false;
console.log(a+b);		//"abctrue"
console.log(a+c);		//"abcfalse"
```

### 2. 减乘除取模运算中 的隐士转换

- 布尔值在和数字之间做减乘除取模的时候，布尔值会隐式转换成数字true是1，false是0。
- 字符串做减乘除取模时，会尝试转换成数字，如果字符串中全是数字，则将字符串转换成数字类型，如果字符串中有非数字字符，则运算结果返回NaN。

```js

```

## 第三节 强制转换

> parseInt() Number() Boolean()
>
> js除了在运算中做隐式转换外，还提供了一些函数给用户，用户可以强制转换某个数据类型

### 1. parseInt()

- 尝试将字符串转换成数字类型
- 如果字符串的内容是纯数字
- 字符串的内容是数字开头
- 字符串的内容非数字开头

### 2. Number()

- 将数据转换成数字
- 内容是纯数字的字符串，会转换成数字。
- 布尔值会转换成数字。
- 字符串中有非数字 就抓换成NaN

### 3. Boolean()

- 将数据类型转换成布尔值
- 转换成fasle的几种情况：false，undefined，0，空字符串（“”），NaN，null，
- 转换成true的几种情况：true，非0数字，非空字符串，对象，数组，对象集合。

## 第四节  赋值运算

> 在做加减乘除取模运算你的时候，js提供了一些简写方式

### 1. 赋值简便写法

- 给某个值做加减乘除法运算的简写方法之一

```js
var a = 10;
a = a+5;		//先计算右侧，再从新赋值给a  运算顺序是 a=10+5  ==>  a=15

var b = 20;
b = b-5;		//b=20-5;  ==>   b=15

var c = 30;
c = c*2;		//60

var d = 40;
d = d/10;		//4

var e = 50;
e = e%20;    	//10
```

### 2. +=  -=   *=  /=  %=

- 语法：`a+=5;`,`a-=5`。

```js
var a = 10;
a+=2;		//a=a+2;		12

var b = 20;
b-=5;		//b=b-5			15	

var c = 30;
c*=2;		//60

var d = 40;
d/=10;		//4

var e = 50;
e%=20 		//10
```

## 第五节 关系运算

> 判断两个数据的关系

### 1. 对比两个值的大小

| >    | <    | >=   | <=   | ==   | ===  | !=   | !==  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 大于   | 小于   | 大于等于 | 小于等于 | 等于   | 强等于  | 不等于  | 强不等于 |

-  简单的对比两个值的大小,结果返回布尔值。
-  此处需要注意的是，js`=`是赋值，`==`才是判断两侧是否相等。

```js
var a = 10;
var b = 15;
var c = 15;

console.log(a>b)		//false
console.log(a<b)		//true
console.log(b>=c)		//true		15>=15
```

## 第六节 逻辑运算

> && || ！

### 1.逻辑 与

- 运算符`&&`，代表并且的意思，即运算符两侧的条件，都要返回true，才会认为整个语句是真。

```js
var a = 10;
var b = 5;
var flag = a>8 && b<7;
console.log(flag); 		//true
var flag1 = a>10&&b>10;
console.log(flag1)		//false
```

### 2.逻辑 或

- 运算符 `||`，代表 或者 的意思，即预算符两侧有一个运算符返回true，就会认为整个语句是true

```js
var a = 10;
var b = 5;
var flag = a>8 || b<7;		
console.log(flag);			//true
var flag1 = a>10 || b>10;	
console.log(flag1)			//true
```

### 3. 逻辑 非

- 运算符 `!`，代表取反的意思，如果某个值是true，取反就是false。

```js
var a = true;
console.log(!a);		false

var b = 10;
var c = 5;
console.log( b>c )		//true
console.log( !(b>c) )	//false
```

# 第五章 逻辑

> js代码在执行的时候，默认是从上逐行向下执行，在js中，有一些语法，能够控制语句的执行顺序
>
> js语句的执行顺序有三种
>
> 顺序执行 选择执行 循环执行

## 第一节 条件语句 if

### 1.if语句

- if 语句的语法是 `如果...就...`
- if语句是选择执行语句，根据判断条件代码是true和false，选择不同的语句执行。

```js
var a = 10;
var b = 20;
if(a<b){		//条件为真才执行下面的代码
  	console.log("a小于b")
}
```

### 2. if...else...

- 如果条件是true，就做什么，否则做什么。
- 一个条件语句，只能执行其中的一处代码，不可能执行多行。

```js
var a = 10;
var b = 20;
if(a<b){		
  	console.log("a小于b")		//此处是条件为真执行的代码
}else{
  	console.log("a大于b或者a等于b")		////此处是条件为假执行的代码
}

var c = 10;
var d = 5;
if(c<d){
  	console.log("c小于d")
}else{
  	console.log("c大于d或者c等于d")
}
```

### 3. if...else if...

- 如果条件1是true，就执行条件1的代码，如果条件2是true，就执行条件2的代码........否则执行。
- 一个条件语句，只会走一个分支，从上向下判断，如果条件是true，就不会继续向下判断了，只会执行条件是true的代码块。

```js
var score = 85;
if(score>85){
  	console.log("成绩是A")
}else if(score>80){
  	console.log("成绩是A-")
}else if(score>75){
 	console.log("成绩是B+")  
}else{
    console.log("加油啊")  
}
```

## 第二节 分支语句 switch

- switch也是选择执行语句，用户可以根据数据的值得不同，执行不同的代码。
- 关键字 break，代码执行到此处，截断代码，不会继续执行后面的switch语句。
- 关键字 deauflt，如果上面的case条件都不对，执行deauflt语句。

```js
var score = "B+"
switch(score){
  	case "A":
    console.log("成绩是A，得分在85到89分");		//此处是值为value1要执行的代码
    break;				//关键字，代表截断，代码不会继续向下执行
    case "A-":
    console.log("成绩是A-，得分在80到84之间")；
    default:
    console.log("加油呀")
}
```

# 第六章 循环

> js语句的执行顺序有三种 顺序执行 选择执行 循环执行
>
> 循环语句的执行顺序就是循环执行

## 第一节 while循环

- 判断条件为true，就执行循环体，知道条件为假，就跳出循环。
- 循环语句可以做一些重复的事情
- while循环的条件，不能一直是真，如果一直是真，代码就会一直循环，造成内存过载，程序崩溃，俗称**死循环**。

```js
//打印三遍 火星时代
var i = 0;
while(i<3){
  	console.log("火星时代");
  	i++;
}
//代码的执行顺序是，先判断条件，条件是true就执行代码块，最后i++;执行完代码块，再判断条件，继续执行代码块，知道条件为假，就停止执行循环。
```

## 第二节 do whild循环

- 和while循环一样，也是循环执行，区别是，while循环是先判断再执行，条件必须是真才执行。do while循环不管条件是否是true，都先执行一次，也就是先执行，再判断。

```js
var a = 1;
do{
  	console.log("先打印一下再说");
}while(a>10)		//条件不成立，但是控制台也会打印一次
```

## 第三节 for循环

### 1. for循环简介

- for循环是最常用的循环。
- 语法：`for(1声明变量;2判断条件;4变量改变){3执行语句}`
- for循环的执行速度非常快，只要不是死循环，几乎瞬间就执行结束了。

```js
for(var i=0;i<3;i++){
  	console.log("火星时代")；
}
console.log(i)
//循环的代码执行顺序是
//1 先申明变量i=0
//2 判断代码是否<3，即条件是否成立
//3 执行语句
//4 条件改变
//之后继续执行 2 3 4。 直到条件假，跳出循环。

//循环结束后，console.log(i)在控制台打印的i是3
```

### 2. for循环循环固定次数

```js
for(var i=0;i<5;i++){	//如果从i=0开始，后面i小于几，就循环几次
  	console.log(i);
}
//0 1 2 3 4 

```

### 3. for循环从m到n

```js
for(var i=3;i<=8;i++){
  	console.log(i)
}
//3 4 5 6 7
```

### 4. for循环从n到m

```js
for(var i=5;i>=2;i--){
  	console.log(i)
}
//5 4 3 2
```

### 5.for循环遍历数组

- 遍历：是指沿着某条搜索路线，依次对数据每个结点均做一次且仅做一次访问。

```js
var arr = ["aa","bb","cc","dd","ee","ff"]
console.log(arr.length);		//6
for(var i=0;i<arr.length;i++){		//数组的长度是5，i的最大值是5，正好可以打印出最后一个元素
  	console.log(arr[i])
}
```

### for循环需要注意的地方

- for循环用两个分号`;`隔开了三条语句，每条语句可以写多句话，用`,`逗号分隔

- 如果中间条件部分有多个语句，以最后一条语句为最终条件

```js
for(var i=0, j=0; j<6, i<4; i++, j++){
    k = i + j;
}
console.log(k);

//条件位置不同，结果不同--------------------------------------------
for(var i=0, j=0; i<4, j<6; i++, j++){
    k = i + j;
}
console.log(k)
```



## 第四节 continue

- continue只能在循环中出现
- continue出现后，循环体中continue代码后面的代码，不会执行，而是执行下一次循环

```js
for(var i=0;i<5;i++){
  	if(i==3){
      continue		//当i等于3的时候，控制台不会打印出3，因为后面的console不会执行
  	}
  	console.log(i);		//0 1 2 4 		没有3
}
```

## 第五节 break

- break只能在循环中出现
- break代表截断，所以在循环中，出现break，循环立即跳出，不会继续循环。

```js
for(var i=0;i<5;i++){
  	if(i==3){
      break		//当i等于3的时候，循环体结束，不会继续执行
  	}
  	console.log(i);		//0 1 2  		没有3
}
```



# 第七章 函数

## 第一节 函数基础

### 1. 声明

- 函数是使用`function`关键字声明，由若干行代码组成的代码块。
- 函数可以解决代码重复的问题

```js
function run(){			//字面量声明方式
  	console.log("你好")；
    console.log("世界")
};
//-----------------------------------------
var run = function(){		//变量赋值方式
  	console.log("你好")；
    console.log("世界")
}
```

### 2. 函数调用

- 函数声明之后，不调用的话，代码不会主动执行。
- 调用函数，可以执行函数。
- 将函数赋值给事件，让事件触发函数调用。
- 函数名加`()`后，会立即调用。

```js
function run(){			//字面量声明方式
  	console.log("你好")；
    console.log("世界")
};

run();		//调用函数

var oBox = document.getElementById("box");		//后面的课程会详细学习，找到页面中id值是box的元素
oBox.onclick = run;		//点击oBox会调用run函数
```

## 第二节  变量作用域

### 1. 什么是变量作用域

> JavaScript 使用var声明变量，在函数内和函数内声明的变量，是有区别的，函数内部声明的变量，函数内部的语句，能够读取到变量，在函数外的程序，是无法读取到该变量的。这就是变量的作用域。

## 2 全局变量

- 没有声明在函数内的变量，叫做全局变量。
- 全局变量的作用域是全局，即函数任何位置的代码，都能够读取到该数据。

```js
var a = 10;		//声明全局变量a
console.log(a)	//可以读取到变量a
function run(){
  	console.log(a);		//这里的代码，在函数内，也可以读取到全局变量a
}
run();
```

## 3. 局部变量

- 在函数中使用关键字`var`声明的变量，叫做局部变量。
- 局部变量的作用域是，只有函数内部的代码可以读取到该局部变量，函数外的代码，读取不到函数内的变量。

```js
var a = 10;				//全局变量
function run(){
  	var b = 20;			//局部变量
  	console.log(a);		//10
  	console.log(b);		//20
}
run();
console.log(b);			//程序报错，因为变量b在函数中，是局部变量，外面读取不到变量b，而全局变量中没有变量b
```

- 不使用`var `声明的变量，是全局变量。

```js
function run(){
  	a = 10;
  	var b= 20; 
}
run()
console.log(a);
console.log(b);
```

### 4. 作用域链

> 如果函数是层层嵌套的，那么每个函数都会有自己的作用域，内层函数能够读取外层函数中的数据，如果内部函数想要找某个数据，会先从当前作用域内找，如果没有找到，会继续想上一级作用域内查找，直到找到数据为止。

- 最内层的函数，可以逐级向外层查找变量，形成的链条，就是作用域链。

```js
var a = 10;
function fn(){
  	var b = 20;
  	console.log(a);		//10
  	function fn1(){
      	var c = 30;
      	var a = 50;
      	console.log(c);		//30
      	console.log(b);		//20
      	console.log(a);		//50		//此处先找当前作用域
  	}
  	fn1()
}
```

## 第三节 函数参数

### 1.函数形参

- 形式参数，在函数未调用的时候，无实际含义，仅用于占位，在函数调用的时候，根据实参确定自己的值。

```js
function sayName(txt){
  	console.log("我的名字叫"+txt);		//定义函数的时候，用txt形参来占位，当实际调用函数的时候，值来自于实参
}
```

### 2.函数实参

- 实际参数，函数调用时候，给形参赋值，形参参与函数运算。

```js
function sayName(txt){
  	console.log("我的名字叫"+txt);		//定义函数的时候，用txt形参来占位，当实际调用函数的时候，值来自于实参
}

sayName("张三")	//我的名字叫张三
//此处字符串张三就是实参
```

- 实参的类型可以是，字符串，数字，布尔值，对象，函数。

### 3. 函数参数总结

- 形参：定义函数的时候用于占位。
- 实参：调用函数的时候，传递真是数据，参与函数运算。
- 形参和实参一一对应。
- 实参少，则多余的形参，值是undefined。
- 实参多，超出形参的参数，无实际意义。
- 传递实参时，可用null占位。

```js
function say(name,age,job){
  	console.log("我的姓名是"+name+",年龄是"+age+",工作是"+job)
    //我的姓名是zhangsan,年龄是null,工作是teacher
}

say("zhangsan",null,"teacher");
```

## 第四节 函数返回值

### 1. 函数返回值是什么

> 函数返回值就是函数运行结束后，返回给你的数据。

- 每个函数，只有一个返回值。
- 使用关键字`return`设置函数的返回值。
- 函数返回值可以是任何数据类型。

```js
function calc(a,b){
  	var c = a*b;
  	return c;		//c是函数的返回值
}
```

### 2.return

- return只能出现在函数中，有两层作用。
- return代表截断函数，函数中出现return，return后面的代码不会被执行。
- return 后面可以跟随一个数据，代表函数的返回值。
- return 后面如果没有跟随数据，返回值为undefined。

```js
function run(){
	console.log(1);
    return;				//return后面没有跟随数据，所以函数的返回值是undefined
  	console.log(2);		//不会执行，因为return后面的代码，不会被执行
}
```

### 3. 函数返回值给变量

- 通常定义一个变量用于存放函数的返回值

```js
function calc(a,b){
  	var c = a*b;
  	return c;		//c是函数的返回值
}
var num = calc(10,20);	//先调用函数，再将函数的返回值赋值给变量num
console.log(num);		200

function run(){
  	console.log(100);	//100
  	return;
  	console.log(200);		//不会执行
}
var returnVal = run();
console.log(returnVal)		//undefined
```

### 4. 函数返回值参与运算

- 函数的返回值，不仅可以赋值给变量，也可以直接参与js的其他运算。

```js
function calc(a,b){
  	var c = a+b;
  	return c;
}
var sum = 100+calc(10,20);
console.log(sum)		//130
console.log(calc(100,200))	//300
```

### 5. 复杂的函数返回值

- 因为函数只能有一个函数返回值，但如果某个函数，需要返回大量的数据的时候，我们可以将数据写成其他数据格式，比如数组，对象等。

```js
//封装一个函数，得到两个数字的加法 减法 乘法 除法 的值。
//因为函数只能有一个返回值，所以把所有计算出来的值，放在一个数组里，把这个数组作为函数的返回值。
function calc(a,b){		
  	var arr = [];
  	var num1 = a+b;
  	var num2 = a-b;
  	var num3 = a*b;
  	var num4 = a/b;
  	arr.push(num1,num2,num3,num4);
  	return arr;
}
console.log(calc(10,5))		//[15, 5, 50, 2]
```

## 第五节 递归函数

- 在函数内部，可以调用其他函数。如果一个函数在内部调用自己本身，这个函数就是递归函数。

```js
//计算阶乘 案例
//n! = 1 x 2 x 3 x ... x n，用函数fact(n)表示，可以看出
var ret = 1;
function fact(n) {
  ret *= n;
  if(n>1){
    fact(n-1)
  }

}
fact(5);
console.log(ret)	//120
```

# 第八章 数据和JSON

## 第一节  数据类型

> JS是一门弱类型语言，定义一个变量的时候，不用同时声明变量的数据类型，因此在变量从新赋值的时候，它的数据类型也会跟随转换

```js
var a = "火星时代";	//string
a = 15;	//number
```

### 1. typeof 得到的数据类型

- js有不同的数据，数据结构有undefined，boolean，number，string，null，array，  object，  function(){}
- typeof 运算符能获取到的数据类型有六种
  - number	数字
  - string  字符串
  - boolean  布尔值
  - object  对象
  - function  函数
  - undefined 

```js
var a;				//undefined
var b = true;		//boolean
var c = 15;			//number
var d = "火星时代";	 //string
var e = null;		//null
var f = ['火星时代','火星时代','火星时代'];		//array
var g = {};			//object
var h = function(){};//function
```



### 2. 值类型和引用类型

- 值类型：值类型的值在存储空间中占用的内存是固定大小的，保存在栈内存中
  - undefined，boolean，number，null， string

```js
var a = 100;
var b =a;	//把a的值赋值给b
a=200;
console.log(b);	//100
```

- 引用类型：引用类型的值不是固定的，因此不能确定它在内存中占用空间的大小，所以保存在堆内存中，拥有一个地址，引用类型的数据指向一个地址
  - array  object  function(){}

```js
var a = {n:1};
var b = a;	//把a的地址给b，a和b指向同一个内存
a.n = 2;
console.log(b.n) //2
```

## 第二节 JSON

### 1. 什么是JSON

- JSON 是一种轻量级的数据交换格式，
- 它基于ECMAScript的一个子集，JSON 使用 JavaScript 语法来描述数据对象（JSON本身就是对象）
- JSON 独立于语言和平台

### 2. JSON 语法

- 内部用 键(key) / 值(value) 进行描述，没有 索引值 和 length属性
- JSON 值可以是以下几种类型：string number boolean array obj null
- JSON 键(key) 必须使用双引号（不能使用单引号）
- JSON 值(value)中的字符串(string)，必须使用双引号（不能使用单引号）
- JSON 值(value)的数字必须是十进制的
- 数组或对象最后一个成员的后面，不能加逗号
- JSON中的key和value通常使用英文，如需使用中文，通常使用unicode编码
- JSON的序列化与反序列化
  - 序列化JSON.stringify( obj )，把一个对象转化成字符串类型
  - 反序列化var Obj= JSON.parse(str)，把字符串转化成对象

### 3. 遍历JSON

- for in 循环 

```js
var obj = {
  "name":"zhangsan",
  "age":18
}
for(var key in obj){
  console.log(obj[key])	//在遍历中key是字符串类型的，所以不能使用.语法读取值
}
```



### 4. 注意事项

- 理论上说，JSON就是JS对象，但两者是有区别的,书写JSON的注意事项:

  - 数组或对象之中的字符串必须使用双引号，不能使用单引号
  - 对象的成员名称必须使用双引号

  ```js
  {'user' : 'zhangsan'}	//不合法
  {"user": 'zhangsan'}	//不合法
  {"user" : "zhangsan"}	//合法
  ```

  - 数组或对象最后一个成员的后面，不能加逗号
  - 数组或对象的每个成员的值，可以是简单值，也可以是复合值。简单值分为四种：
    - 字符串、数值（必须以十进制表示）、布尔值和null（NaN, Infinity, -Infinity和undefined都会被转为null）
  - 复合值分为两种：符合JSON格式的对象和符合JSON格式的数组。

  ```js
  {"age" : ox16}//不合法,数值必须是十进制的
  {"city" : undefined}//使用undefined,不合法
  {"city" : null,"getcity": function() { console.log("错误用法");}}​​
  ```


## 第三节 XML

- 可扩展标记语言(eXtensible Markup Language)，是一种用于标记电子文件使其具有结构性的标记语言。
- 它和超文本标记语言语法区别：超文本标记语言的标记不是所有的都需要成对出现，它则要求所有的标记必须成对出现；HTML标记不区分大小写，它则大小敏感，即区分大小写。

```xml
<CATALOG><!--目录-->
	<CD>
		<TITLE>只知道此刻爱你</TITLE>
		<ARTIST>刘德华</ARTIST>
		<COUNTRY>中国 香港</COUNTRY>
		<COMPANY>华星唱片</COMPANY>
		<PRICE>10.90</PRICE>
		<YEAR>1986</YEAR>
	</CD>
	<CD>
		<TITLE>回到你身边</TITLE>
		<ARTIST>刘德华</ARTIST>
		<COUNTRY>中国 香港</COUNTRY>
		<COMPANY>百代唱片</COMPANY>
		<PRICE>9.90</PRICE>
		<YEAR>1988</YEAR>
	</CD>
</CATALOG>
```





# 第九章 函数高级部分

## 第一节 函数基础

- 在JS中函数是一种数据类型。
- 函数代表一段代码。
- 函数表示一个行为或功能。

```js
function foo(){
	console.log(1)
}

var bar = function fun(){
	console.log(2)
}
var a = bar;
var b = foo;
```

- 函数是不会主动执行的，一定要有人调用才会执行。
- 事件与回调都是依赖内部机制调用的。
- 函数的调用就是把实参赋值给形参，然后函数中的代码从头到尾的执行一遍。
- 可以把整个函数调用当作 其对应的返回值来用。

```js
function foo(){
	return 1;
};
var a = foo() + 2;
```

- 匿名函数: 函数名就一个作用，方便调用。如果不需要直接调用，那么名字就不重要的。
- 匿名函数的主要作用就是为了消除全局变量污染。


- 自运行函数创建一个运行空间，所有的变量的作用域都在这个空间内。内部定义的变量不会和外部的变量发生冲突

```js
(function(){
	var a = 1;
})()
console.log(a) //a is not defind
```

## 第二节 实参对象arguments

### 1. 形参和实参

- 形参（parameter）：函数定义时圆括号里的数据。
- 实参（arguments）；函数调用时，传给函数作为参数的数据。可传入任意数量，任意类型的参数，可以不跟函数定义时传入的形参数量相对应。
  - 实参和形参在数量上，类型上、顺序上应严格一致，否则就会发生类型不匹配的错误
  - 必要的参数定义在前面，不必要的参数，放在后面
  - 在传参时，如果不想传递某个实参，可以用null占位

```js
function setStyle(obj,mode,value){
  obj.style[mode] = value;
}
setStyle(oBox,"width","50px");
setStyle(oBox,"50px"); // 不执行
```

### 2. arguments

- arguments : 是一个类数组对象，包含着传入函数中的所有参数。用arguments可以获取实参的数组。

```js
function sum(){
  	var res = 0;
  	for(var i=0;i<arguments.length;i++){
      	res+= arguments[i]
  	};
  	return res
};
sum(1,3,5,7,9)		//25
```

## 第三节 函数参数的使用技巧

### 1. 参数的默认值

- 调用时实参的个数可以和形参的个数不一样。
- 如果实参的个数少，那么对应的形参就相当没有赋值（undefined）。

```js
function foo(msg){
	console.log(msg);
}
foo(); // 输出undefined
//---------------------------------------
function foo(msg){
  	if (msg === undefined){
      msg = "default";
    }
	console.log(msg);
}
foo();
//----------------------------------------
function foo(msg){
msg = msg || "default"; 
console.log(msg);
}
foo();
```

- 如果实参比形参多，那么多余的实参就没有赋值给任何形参。
  - 拖拽案例，增加标题拖拽
- 设计的技巧：通常会把可变长参数放在最后。

```js
function foo(a, b){
	console.log(a+b);
}
setTimeout(foo, 1000, 10, 20);

setTimeout(function(){
  foo(10,20)
},1000)

oBox.addEventListener('click',function(ev){	//事件对象
  console.log(ev);
  foo(10,30)
},false)
```



### 2. 函数的重载

> 函数重载是指在同一作用域内，可以有一组具有相同函数名，不同参数列表的函数，这组函数被称为重载函数。重载函数通常用来命名一组功能相似的函数，这样做减少了函数名的数量，避免了名字空间的污染，对于程序的可读性有很大的好处。

- 同名变量的定义，后一个会覆盖前一个。所以JS中没有函数的重载。
- 我们这里讲的重载是指赋予一个函数多个功能。根据参数个数或者类型不一样来区分对应的功能。

```js
var a = 1;
var a = 2;
console.log(a); //输出：2 。 后一个定义会覆盖之前的同名定义。
//-------------------------------------------
function add(a, b){
	return a+ b;
};
function add(a, b, c){
	return a + b + c;
};
// 后一个定义会覆盖之前的同名定义。
```

```js
function a(){
	console.log("hello world.");
}
var a = 1; // 覆盖了a函数的定义。

console.log(a);
a(); // ERROR
```

- get | set 型重载

```js
function height(obj,b){
  	if(b === undefined){
    	return obj.offsetHeight;
  	}else{
    	obj.style.height = b+"px";
 	}
}
```

- value | string 型重载

```js
function height(obj,start,speed){
  var mode = {
    slow:1000,
    normal:500,
    fast:100,
  };
  var i=0;
  if(typeof speed == "string"){
    speed = mode[speed]
  }
  setInterval(function(){
    i++
    obj.style.height = start+i+"px";
  },speed)
};
//预先定义一些数据，根据传递参数不同，读取不同的值
//让盒子变高
```

- 案例字体大小
- value | {} 型重载
  - 这种重载允许我们同时传多个值。

```js
var oBox = document.getElementById("box");
function setStyle(obj,a,b){
  if(b){
    obj.style[a] = b;
  }else{
    for(var key in a){
      obj.style[key] = a[key];
    }
  }
};
setStyle(oBox,"height","200px");
setStyle(oBox,{"width":"200px","height":"300px"})
```

## 第四节 回调函数

### 1. 回调函数

- 把一个函数a当做参数，传递给另外一个函数b，作为函数b的实参。在函数b运行时，可以调用函数a

```js
function a(){
	console.log(1);
}
function b(x,y,fn){
	if(x>y){
		fn&&fn()		//短路
	}else{
		console.log(0)
	}
};
b(1,2,a) // 0
b(10,2,a) // 1
```

### 2. js单线程和异步

- js是单线程语言，同一时间只能做一件事，只有当做完当前的事情，才会做其他的事情
- 所有要做的事情，都存放在一个队列中。主线程做一件事，做完之后，队列中的一个任务进入主线程。
- 计时器，ajax是异步操作，先放在队列中等待执行，主线程执行完，才会继续执行。

```js
setTimeout(function(){
	console.log(1)
},1000);
console.log(2);
//先提示2，再提示1
```

## 第五节 自运行函数

- 声明和运行在一起的函数叫做自运行函数

```js
(function(){
  alert(1)
})()
//会立即执行，不参与预解析
```

- 自运行函数可以进行变量保护，有自己的作用域。
- 自运行性函数定义的那个function在全局作用域下不进行预解析，当代码执行到这个位置的时候，定义和执行一起完成了。
- 自运行函数后面必须写`；`
- 下一行如果是`（`  `[`  `/`  `+`  `-`  符号开头，本行必须加`;`

## 第六节 闭包

### 1. 闭包的概念

- 闭包一定是一个函数，这个函数有权访问和操作其他函数作用域中的数据

### 2. 闭包的几种创建方式

- 1、在一个函数内部创建另外一个函数，并且把这个函数return出去。
- 2、用函数为元素绑定事件，当事件发生时，还可以操作该函数中的变量。  

```js
//第一重方式----函数内部return一个函数
function foo(){
  var i=0;
  return function(){
    i++;
    console.log(i)
  }
}
var fn = foo();
fn();
```

```js
var aLi = document.getElementsByTagName('li')
for(var index=0;index<10;index++){
  (function(i){
    aLi[i].onclick = function(){
      console.log(i)
    }
  })(index)
}
```

```js
//第二种方式--函数内部为绑定事件
function addClick(){
  var txt="hxsd";
  document.getElementById('box').onclick=function(){
    alert(txt);
  }
};    
addClick();
```

```js
//第三种方式--函数内部将变量作为回调函数的参数
function play(num,fn){
  if(num>10){
    return fn && fn(num);
  };
};

var ss=play(20,function(n){
  return n+1;
});
```





## 第七节 全局函数

- 在之前学习BOM时候，BOM提供给我们一些可以直接调用的方法，alert，setTimeout
- js语言也给我们提供了几个函数，其作用域是全局，叫做全局函数。(后期增加了全局函数，经常用的如下)
  - parseInt():返回转换成整数的值
  - parseFloat():返回转换成浮点型的值。
  - isFinite(value):检测某个是是否是无穷大。
  - isNaN(value)：检测某个值是否是NaN。
  - eval()：将JavaScript字符串当作脚本来执行

```js
eval("console.log(111)")	//111
```

- 全部函数和BOM方法是有区别的，一个是javaScript提供的，一个是BOM提供的。



# 第十章 面向对象

> JavaScript是基于对象编程的，面向对象是一种编程思想。

## 第一节 类和对象

- 类：我们善于将事物进行分类，类是一个抽象的概念
- 对象：具体的事物
  - 猫是一类
  - 楼下的大黄 对象
- 类是对象的抽象，对象是类的具体事例
- 类不占用内存，对象占用内存空间
- 对象的访问
- 声明对象
  - 字面量声明 var obj = {}
  - new运算符

```js
var obj = new Object();
```

- 定义对象的属性和方法
  - .语法 ：oBox.id = "abc"
  - []方括号语法 oBox["id"]= "abc"
- 遍历对象
  - for in 循环
  - 多用于遍历json

```js
var obj = {
  name:"hxsd",
  age:20,
}
for(var key in obj){
  console.log(key,obj[key])
}
//name,hxsd
//age,20
```

- 检测对象有没有某个属性

```js
if ("name" in obj)
if (obj.name === undefined)
```

- 删除对象的属性`delete arr.name`

## 第二节 创建对象

### 1. 字面量创建

- 假如我们把猫看成是一类，有名字和姓名的属性

```js
var Cat = {
  name:"",
  color:"",
}
```

```js
var cat1 = {
  name:"大黄",
  color:"黄色",
  say:function(){
    alert("miao")
  }
};

var cat2 = {
  name:"小黑",
  color:"黑色",
  say:function(){
    alert("miao")
  }
};
```



- 这样创建对象，一是写起来就非常麻烦，二是实例与原型之间，没有任何办法，可以看出有什么联系。

### 2. 工厂模式

- 可以写一个函数，解决代码重复的问题
- 工厂模式中的函数

```js
function makeCat(n,c){
    return {
        name:n,
        color:c,
        say:function(){
          alert("miao")
        }
    }
}
```

- 生成实例对象，就等于是在调用函数

```js
var cat1 = makeCat("大黄","黄色");
var cat2 = makeCat("小黑","黑色")
```

- 这样代码虽然简单了，但是实例之间还是没有什么联系

### 3. 构造函数

- 为了解决从原型对象生成实例的问题，Javascript提供了一个构造函数（Constructor）模式。
- 所谓"构造函数"，其实就是一个普通函数，但是内部使用了`this`变量。对构造函数使用`new`运算符，就能生成实例，并且`this`变量会绑定在实例对象上。
- 构造函数首字母大写
- 构造函数中的this，指向的事实例化的对象

```js
function Cat(n,c){
  this.name=n;
  this.color=c;
}
```

- 生成实例对象

```js
var cat1 = new Cat("大黄","黄色")
var cat2 = new Cat("小黑","黑色")
```

- 这时`cat1`和`cat2`会自动含有一个`constructor`属性，指向它们的构造函数。

```js
alert(cat1.constructor == Cat); //true
alert(cat2.constructor == Cat); //true
```

- Javascript还提供了一个`instanceof`运算符，验证原型对象与实例对象之间的关系。
- instanceof不认为原始类型值的变量是对象

```javascript
var txt='adsdf';
alert(txt instanceof String);//false

var age=123123;
alert(age instanceof Number);//false

var re=/\d/;
alert(re instanceof RegExp);//true

var arr=[];
alert(arr instanceof Array)//true
```

## 第三节 原型和原型链

- 每类对象的实例对象，都有可能会有一些相同的属性，或者相同的功能，如果都写在构造函数上，会造成重复的内容，占用更多的内存。
- 为了解决这种代码的重复
  - 构造函数都有一个`prototype`属性，指向另一个对象。这个对象的所有属性和方法，都会被构造函数的实例继承。
  - 我们可以把那些不变的属性和方法，直接定义在`prototype`对象上。

```js
Cat.protoType.say = function(){
  alert("miao")
}
cat1.say()	//miao
cat2.say()	//miao
```

- 所有的函数都是 Function 的实例。在构造函数上都有一个原型属性---prototype，prototype也是一个对象；这个对象上有一个 constructor 属性，该属性指向的就是构造函数
- 而实例对象上有一个_proto_属性，该属性也指向原型对象，该属性不是标准属性，不可以用在编程中，该属性用于浏览器内部使用。



# 第十一章 内置对象

## 第一节 内置对象种类

- Object  --- 是所有JavaScript对象的超类(基类),JS中的所有对象都是继承自Object对象的
- Array   ---数组对象--定义数组属性和方法
- Boolean  ---布尔对象--布尔值相关
- Error  ---错误对象--处理程序错误
- Function   ---函数对象--定义函数属性和方法
- Math   ---数学对象
- Date   ---日期对象
- RegExp   ---对象正则表达式对象--定义文本匹配与筛选规则 (后面详细讲解)
- String   ---字符串对象--定义字符串属性和方法
- Global  --没有语法，直接调用函数，如 parseInt()
- Number  

## 第二节 Array 方法

- concat() 连接两个或更多的数组，返回一个新的数组，原有数组不会改变

```js
var arr1= ['张三','李四','王五','赵六'];
var arr2 = ['火','星','时','代'];
var arr3 = [1,2,3,4]
var arr = arr.concat(arr2,arr3);	
//["张三", "李四", "王五", "赵六", "火", "星", "时", "代", 1, 2, 3, 4]
console.log(arr)
```

- join() 把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔,并返回结果

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.join(',');
console.log(arr) //'张三,李四,王五,赵六';
console.log(typeof arr) //string
console.log(arr1)//原数组不变
```

- pop() 删除并返回数组的最后一个元素,修改原数组

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.pop();
console.log(arr) //赵六
console.log(typeof arr) //string
console.log(arr1)//['张三','李四','王五']
```

- push() 向数组的末尾添加一个或更多元素，并返回新的长度,修改原数组

```js
var arr1= ['张三','李四','王五','赵六'];
arr1.push('阿七');
console.log(arr1) //['张三','李四','王五','赵六','阿七'];
```

- reverse() 颠倒数组中元素的顺序

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.reverse();
console.log(arr) //["赵六", "王五", "李四", "张三"]
```

- shift() 删除并返回数组的第一个元素,修改原数组

```js
var arr1= ['张三','李四','王五','赵六'];
arr1.shift();
console.log(arr1) //["李四", "王五", "赵六"]
```

- slice() 从某个已有的数组返回选定的元素
  - slice(start,end)   start:规定从何处开始选取。end:从何处结束选取

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.slice(1,3);	//截取1,2下标
console.log(arr1) //["张三", "李四", "王五", "赵六"]
console.log(arr) //["李四", "王五"]
```

- sort() 对数组的元素进行排序  参数必须是个函数 arr.sort( function(a,b){ return a-b } )

```js
var arr = [2,5,1,6,3];
arr.sort( function(a,b){ return a-b } )
console.log(arr)	// [1, 2, 3, 5, 6]
```

- splice() 插入 删除  替换  数组的元素,返回新数组

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.splice(1,3)
console.log(arr);	//删除   从索引1开始，数量是3个，["李四", "王五", "赵六"]
console.log(arr1) //["张三"]
```

```js
var arr1= ['张三','李四','王五','赵六'];
var arr = arr1.splice(1,3,"哈哈","吼吼");	//替换   从索引1开始，数量是3个，用后面的替换，如果第二个参数是0，就是添加
console.log(arr);	//替换  从索引1开始，数量是3个，["李四", "王五", "赵六"]
console.log(arr1) //["张三", "哈哈", "吼吼"]
```

- toString() 把数组转换为字符串，并返回结果

```js
var arr1= ['张三','李四','王五','赵六'];
var str = arr1.toString();
console.log(str);		//string  "张三,李四,王五,赵六"
console.log(arr1)
```

- indexOf()  查询某个元素在数组中首次出现的位置，如果出现返回下标，没有出现，返回-1
- forEach() 循环遍历数组中的每一个元素
  - forEach() 内写一个函数，函数接受三个参数`forEach( function (item,index, array) {}) `
  - item 表示每次迭代的元素
  - index 表示每次迭代元素的下标

  - array 表示原数组
- map()  返回一个新数组，新数组是原数组的映射；

  - 不改变原数组的值；
  - 新数组的元素值是每次函数return的返回值；
  - 若不写return，接收的新数组的元素值将全为空；

```js
var arr = [20,13,11,8,0,11];
var brr = arr.map(function(item){
	return item*1.2;
	// 此时brr为a数组每个元素的1.2倍
	//若return 1，则新数组的每个元素值均为1
	//return 1;
})
console.log(brr);	//[24, 15.6, 13.2, 9.6, 0, 13.2]
```

- filter()  过滤元素，返回一个新数组；
  - 新的数组由每次函数返回值为true对应的元素组成；
  - 原数组不受影响

```js
var arr = [20,13,11,8,0,11];
var brr =arr.filter(function(item){
	//返回值为奇数的元素
	return item%2;
})
console.log(brr)	//[13, 11, 11]
```

- some()  验证数组中是否有元素满足条件
  - return返回的值只要有一项为true,最终的返回值就为true,不会继续遍历后边的元素；若没有一项满足返回值为true的，就返回false；
  - 原数组不受影响；

```js
var arr = [20,13,11,8,0,11];
var brr = arr.some(function(item){
	return item>10;
})
alert(brr); //true
```

- every()  验证数组中是否每个元素都满足条件
  - 对数组的每一项执行给定的函数，假如该函数每一项都返回true，最后结果才为true；
    只要有一项返回值为false，最后结果就是false。且后边的元素都不会再继续执行函数；
  - 原数组不受影响；

```js
var arr = [20,13,11,8,0,11];
var brr = arr.every(function(item){
	return item>10;
})
alert(brr); //false
```



## 第三节 Math 方法

- Math.abs(x)	返回数的绝对值 （去除正负）
- Math.random()随机数     0-1之间的随机数，1不会出现

```js
Math.random() 				//0-1之间，不会出现1
Math.random()*10          	//0-10之间的浮点数 0 ---9.xxx
parseInt(Math.random()*10) 	//取整后 0-9
parseInt(Math.random()*11)  // 0-10 
parseInt(Math.random()*10+1)// 1-10
Math.random()*(90-30)+30	//30－90	不包含90
```

- Math.random()*(大－小)+小 parseInt后 不包含“大”
  - rend函数封装
- Math.round(x)四舍五入
- Math.floor(x)下舍入(向下取整)

```js
var a = 12.6;
var b = -1.2;
var a1 = Math.floor(a);		//12
var b1 = Math.floor(b);		//-2
```

- Math.ceil(x)上舍入(向上取整)

```js
var a = 12.6;
var b = -1.2;
var a1 = Math.ceil(a);		//13
var b1 = Math.ceil(b);		//-1
```

- Math.max(x,y)返回 x 和 y 中的最高值
- Math.min(x,y)返回 x 和 y 中的最低值
- Math.cos(x)返回x的余弦
- Math.sin(x)返回x的正弦
- Math.sqrt(x)返回x的平方根

## 第四节 Date 方法

- getFullYear()	返回年

- getMonth()返回月份0--11
- getDate()返回某一天。

- getDay()返回星期0-6

- getHours()返回小时

- getMinutes()返回分钟

- getSeconds()返回秒

- getTime()返回1970年1月1日午夜到指定日期（字符串）的毫秒数

- setFullYear()设置年份

  ```js
  setFullYear(year，month，day)	
  //year：必需，表示年份的四位整数
  //month：可选,介于 0 ~ 11 之间：如果不填，取系统当月
    //-1为去年的最后一个月,12为明年的第一个月
    //13为明年的第二个月
  //day：可选,表示月中某一天的数值。如果不填，取系统当日
    //用本地时间表示。介于 1 ~ 31 之间：
    //0 为上个月最后一天
    //-1 为上个月最后一天之前的天数
    //如果当月有31天: 32 为下个月的第一天
    //如果当月有30天: 32 为下一个月的第二天
  ```

- setMouth()设置月
- setDate()设置天

- setHours()设置小时

  ```js
  setHours(hour,min,sec,millisec)
  //可以有4个参数
  //hour：小时
  //min：分钟
  //sec：秒
  //millisec：毫秒
  ```

- setMinutes()设置分钟
- setSeconds()设置秒

- setTime()使用毫秒的形式设置时间对象

- ★注意:setDay( 这个真没有!!!!,星期是通过设定日期自动计算的 )

- 1秒=1000毫秒

- 1分钟=60秒

- 1小时=60分=3600秒

- 1天=24小时=1440分=86400秒

```js
//例：现在时间：13:11:43
var date = new Date(2012, 2, 15, 13, 11, 43);
//2012年3月15日 13:11:43
```

- 判断闰年:

```js
function runYear(year){
	if(year%4==0 && year%100!=0 || year%400==0){
		return true;
	}
};
```

  案例：倒计日

  案例：倒计时

## 第五节 String 方法

- slice(start[,end])    start--开始索引   end--结束索引

```js
var str = 'hxsdweb';
var str1 = str.slice(1, 4);	//开始索引值，结束索引值（不包含）
console.log(str1);
console.log(str)
var str2 = str.slice(2);	//如果不写结束位置，一直复制到最后
console.log(str2)
var str3 = str.slice(1, -1);//负值 是倒数的意思
console.log(str3)
```

- substr(start[,length])  start开始，取length个字符

```js
var str = "火星时代教育";
var str1 = str.substr(2,4);	//时代教育
```

- split([separator[,limit]])  按条件分割字符串，保存成数组

```js
var str = "火星时代教育";
var arr = str.split("");	 //["火", "星", "时", "代", "教", "育"]
var str1 = "杏|石|口|路|81|号";
var arr1 = str1.split("|");	 //["杏", "石", "口", "路", "81", "号"]
```

- indexOf() （string）在父串中首次出现的位置，从0开始！没有返回-1
- lastIndexOf() 倒序查找
- charAt(index)  指定索引的字符
- toLowerCase 转小写
- toUpperCase 转大写

# 第十二章 正则表达式

## 第一章概念和用途

### 1. 概念

- 正则表达式 regular expression（有规律的 表达 ）
- 一个正则表达式就是由普通字符（例如字符 a 到 z）以及特殊字符（称为元字符）组成的文字模式。
- 正则表达式作为一个模板，将某个字符模式与所搜索的字符串进行匹配。 

### 2. 用途:

- 正则匹配:   可以测试字符串内容是否可以与正则相匹配
- 替换文本:   根据模式匹配字符串中的特定内容，进行替换、删除 
- 提取数据:   根据模式匹配从字符串中提取内容，生成数组 

## 第二节 创建正则表达式：

- new运算符声明：
  - RegExp是一个对象,和Array一样 ，正则表达式的内容作为字符串传递进去

```js
var re = new RegExp("a","i");
//这是个最简单的正则表达式,将匹配字母a，第二个参数i,表示匹配时不分大小写
```

- 字面量声明：

```js
var re=/abc/g;  
//全文匹配abc
```

- 注意: 正则表达式内不要出现空格(除非想匹配空格)

## 第三节 语法

### 1. 正则表达式中的 | [ ] ( ) { }

- | 竖线

  - 左右两边表达式之间 "或" 关系，匹配左边或者右边

  ```js
  /ab|cd/
  //匹配ab 或者 cd
  ```

  - ★注意：竖线两侧视为相互独立的两个部分（与分组不同），可进行分别的匹配操作


- ( )小括号

  - 小括号用于分组

  ```js
  var re = /(ab|cd){2}/
  //匹配字符串"ab" 或者 "cd" 的2次，或者abcd  结果为:abab cdcd abcd cdab
  ```

  - ★注意：小括号、竖线不要放在 [ ] 内（无意义）

- [ ]方括号

  - 用于查找某个范围内的字符：
    - [abc]查找方括号之间的任何字符
    - [0-9]匹配任何从 0 至 9 的数字
    - [a-z]匹配任何从小写 a 到小写 z 的字符
    - [A-Z]匹配任何从大写 A 到大写 Z 的字符
    - [A-z]匹配任何从大写 A 到小写 z 的字符
    - ★注意：`[^abc]`匹配任何 不在 方括号之间的字符


- { }大括号

  - 用于设置量词（非负整数）
    - {n}匹配确定的 n 次
    - {n,}至少匹配n 次    
    - {n,m}最少匹配 n 次, 最多匹配 m 次( 要求: m >= n )
  - 三个简写量词(符号)： 
    - ?匹配零次或一次( 等价于:{0,1} )
    - *匹配零次或多次( 等价于:{0,} ) 
    - +匹配一次或多次( 等价于:{1,} ) 

  案例：匹配国内电话号码： 匹配形式如 0511-4405222 或 021-87888822


- 贪婪量词: 贪婪模式尽可能多的匹配
  - ?  *  +  {n} {n,m} {n,} 


- 惰性量词: 惰性模式尽可能少的匹配
- 用惰性量词进行匹配时，它首先将第一个字符当成一个匹配，如果成功则退出，如果失败，则测试前两个字符，依些增加，直到遇到合适的匹配为止。贪婪量词与贪婪量词的方法正好相反.  惰性量词仅仅在贪婪量词后面加个"?"而已,如"a+"是贪婪匹配的,"a+?"则是惰性的 
  - ??     *?     +?     {n}?     {n,m}?  

```js
var str="abbbbcc"；
//贪婪： 
/[ab]+b/     //结果：abbbb
//惰性： 
/[ab]+?b/    //结果：ab
```

```js
var str = 'aabbazbbwwbbaa';
var arr =str.match(/.*bb/); //aabbazbbwwbb，贪婪的
var arr =str.match(/.*?bb/g); //aabb azbb wwbb 返回一个数组包含3个值，惰性的
```



### 2. 元字符（Metacharacter）

- 元字符是拥有特殊含义的字符：
  - .查找单个字符，除了换行和行结束符
  - \w匹配字母数字和下划线( 等价于:[a-zA-Z0-9_] )
  - \W匹配 除 字母数字下划线之外的字符( 等价于:`[^a-zA-Z0-9_]` )
  - \d匹配数字 ( 等价于:[0-9] )
  - \D匹配 非 数字字符( 等价于:`[^0-9]` )
  - \s匹配一个空白字符( 等价于:[\n\r\t\f\x0B] )
  - \S匹配一个 非 空白字符( 等价于:`[^\n\r\t\f\x0B]` )
  - \b匹配单词边界
  - \B匹配 非 单词边界
  - \0匹配 NUL 字符
  - \n匹配 换行符
  - \f匹配 换页符
  - \r匹配 回车符
  - \t匹配 制表符
  - \v匹配 垂直制表符
- 注意：元字符只能匹配一个字符，通常，元字符后面都会设置量词。

### 3. 直接量字符：

```
\/	匹配 / 
\\	匹配 \ 
\.	匹配 .
\*	匹配  *
\+	匹配 +
\?	匹配 ? 
\|	匹配 |
\(	匹配 (
\)	匹配 )
\[	匹配 [ 
\]	匹配 ]
\{	匹配 {
\}	匹配 }
\’	匹配 单引号
\”	匹配 双引号
\xxx	查找以八进制数 xxx 规定的字符
\xdd	查找以十六进制数 dd 规定的字符
\uxxxx	查找以十六进制数 xxxx 规定的 Unicode 字符
```

### 4. 位置限制

- ^     匹配任何开头为的字符串
- $     匹配任何结尾为的字符串

### 5. 修饰符

- i	忽略大小写
- g      全文查找
- m    多行查找（必须与g一起实用,并且,当使用^和$模式时才会起作用）

## 第四节 正则表达式 方法：

### 1. test

- 检索字符串中指定的值。返回 true 或 false。

- 注意:使用test方法时,g修饰符的差异:

  - 正则内部有个lastIndex属性,这个属性记录每一次匹配后的索引位置,该属性,在于"g"修饰符存在以下关系:

  - 没有 g: 当没有设置g时lastIndex属性的值始终为0，每次执行匹配仅查找字符串中第一个匹配的项。

    ```js
    var txt="this a cat, that a dog";
    var re=/cat/;
    alert(re.test(txt));   //true
    console.log(re.lastIndex);   //索引是0
    alert(re.test(txt));  //true
    ```

  - 有g：找到匹配的项后lastIndex的值被设置为匹配内容的下一个字符的索引,用来标识下次执行匹配时开始查找的位置。如果找不到匹配的项lastIndex的值会被设置为0。

    ```js
    var txt="this is a cat, that is a dog";

    var re=/cat/g;

    alert(re.test(txt));   //true

    console.log(re.lastIndex);   //索引是10

    alert(re.test(txt));  //false
    ```

  - 一般情况下,使用test方法,都不使用g修饰符

### 2. 支持正则的 String 对象方法

- search（）	 第一个与正则相匹配的字符串的索引（不执行全局匹配，它将忽略标志 g）

- match（）     找到一个或多个正则表达式的匹配，没有找到任何匹配的文本，返回 null，否则，返回一个数组

- replace（）   替换与正则表达式匹配的子串

  案例：修改文字

- split（）         把字符串分割为字符串数组

