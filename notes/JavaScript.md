# JavaScript基础

## JavaScript介绍

### JavaScript是什么

> JavaScript 是运行在**客户端**的一种**脚本语言**。

Netscape在最初将其脚本语言命名为LiveScript，后来因与Sun合作之后将其改名为JavaScript。JavaScript最初受Java启发而开始设计，目的之一就是看上去像Java。因此语法上有类似之处，一些名称和命名规范也借自Java。但只是名字很像。

Java的解释器被称为JavaScript引擎，为浏览器的一部分，广泛用于客户端脚本语言，最早是在HTML网页上使用，用来增加动态功能。

JavaScript是什么：

1. 是一门脚本语言
2. 是一门解释性语言
3. 是一门动态类型的语言
4. 是一门基于对象的语言

编译语言：需要把代码翻译成计算机所认知的二进制语言，才能执行。

脚本语言：不需要编译，直接执行。

常见的脚本语言：t-sql、cmd

### JavaScript与HTML、CSS的区别

HTML：标记语言，展示数据的

CSS：美化页面

JS：用户和浏览器交互

### JavaScript现在的意义（应用场景）

1. 网页特效

2. 服务端开发（Node.js）

3. 命令行工具（Node.js）

4. 桌面程序（Electron）

5. App（Cordova）

6. 控制硬件-物联网

7. 游戏开发(cocos2d.js)

   

## JavaScript组成

JavaScript分为三个部分：

1. ECMAScript—js的基本语法

2. DOM—Document Object Model 文档对象模型

3. BOM—Browser Object Modern 浏览器对象模型



### ECMAScript

定义了JavaScript的语法规范  

JavaScript的核心，描述了语言的基本语法和数据类型，ECMAScript是一套标准，定义了一种语言的标准与具体实现无关

### DOM文档对象模型

一套操作页面元素的API

DOM可以把HTML看做是文档树，通过DOM提供的API可以对树上的节点进行操作

### BOM浏览器对象模型

一套操作浏览器功能的API

通过BOM可以操作浏览器窗口，比如：弹出框、控制浏览器跳转、获取分辨率等



## JavaScript代码书写位置

js代码可以写在三个地方：

1. html文件中,`<script>`标签中
2. html的标签中
3. js文件中，需要在html页面中引入 `<script>`标签的`src`属性中



js代码的注意问题

1. 在一对`<script>`的标签中有错误的js代码，那么该错误的代码后面的js代码不会执行。
2. 如果第一对`<script>`标签中有错误，不会影响后面的`<script>`中的js代码执行。
3. `<script>`标准写法是`<script type="text/javascript"> </script>`或`<script language="Javascript"> </script>`，但是如果使用HTML5的写法，type、language可以省略。
4. `<script>`在页面中可以出现多对。
5. `<script>`一般放在body的标签最后，有时也放在head标签中。
6. 如果这对`<script>`标签是引入外部js文件的作用，那么这对标签中不要写任何js代码，如果要写，重新写一堆`<script>`标签。



## 计算机组成

### 软件

- 应用软件：浏览器(Chrome/IE/Firefox)、QQ、Sublime、Word
- 系统软件：Windows、Linux、mac OSX

### 硬件

- 三大件：CPU、内存、硬盘    -- 主板
- 输入设备：鼠标、键盘、手写板、摄像头等
- 输出设备：显示器、打印机、投影仪等

![](/Users/leitianxiao/Documents/GitHub/NoteBooks/100 - Work | 工作/110 - Work -Src | 源 /compute.png)

## 变量

### 什么是变量

- 什么是变量

  变量是计算机内存中存储数据的标识符，根据变量名称可以获取到内存中存储的数据
  
- 为什么要使用变量

  使用变量可以方便的获取或者修改内存中的数据



### 如何使用变量

- var声明变量

```javascript
var age;
```

- 变量的赋值

```javascript
var age;
age = 18;
```

- 同时声明多个变量

```javascript
var age, name, sex;
age = 10;
name = 'zs';
```

- 同时声明多个变量并赋值


```javascript
var age = 10, name = 'zs';
```

### 变量的命名规则和规范

- 规则 - 必须遵守的，不遵守会报错

  - 由字母、数字、下划线、$符号组成，不能以数字开头

  - 不能是关键字和保留字，例如：for、while。

  - 区分大小写

- 规范 - 建议遵守的，不遵守不会报错

  - 变量名必须有意义
  - 遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。例如：userName、userPassword

- 变量声明和变量初始化
  - 变量声明：有var，有变量名，没有值
  - 变量初始化：有var，有变量名，有值

## 注释

### 单行注释

一般用在一行代码的上面

```javascript
//这是单行注释
```

### 多行注释

一般是用在函数或者一段代码上面

```javascript
/*
这是多行注释
*/
```

## 数据类型

原始数据类型：number、string、boolean、null、undefined、object

### Number

数字类型，整数和小数。

- 进制

  - 二进制：遇2进1，计算机只认识二进制，要将其他进制转换成二进制，计算机才能识别。

    ```
    00000001——1
    00000010——2
    00000011——3
    ```

  - 八进制：遇8进1，`0`开头

    ```
    00000001——1
    00000002——2
    00000003——3
    00000004——4
    00000005——5
    00000006——6
    00000007——7
    00000010——8
    ```

  - 十进制：遇10进1，生活中用的就是十进制

    ```
    00000001——1
    00000008——8
    00000009——9
    00000010——10
    00000011——11
    ```

  - 十六进制：遇f进1，0-9以及a-f，用`0x`开头

    ```
    00000001——1
    00000009——9
    0000000a——10
    0000000b——11
    0000000f——15
    00000010——16
    ```

- 数字类型的范围

  最小值：`console.log(Number.MIN_VALUE);//5e-324`

  最大值：`console.log(Number.MAX_VALUE);//1.7976931348623157e+308`

  无穷大：infinity

  无穷小：-infinity

- 数值判断
    
  - NaN：not a number
  
  - NaN 与任何值都不相等，包括他本身
  
    ```javascript
    var num;
    console.log(num+10==NaN);//false
    ```
  
  - isNaN: is not a number
  
    如何验证结果是不是NaN，使用`isNaN()`
  
    ```javascript
    var num;
    console.log(isNaN(num+10));//true
    ```

- 语言缺陷：不要用小数去验证小数

  ```javascript
  var x=0.1;
  var y=0.2;
  var sum=x+y;
  console.log(sum);//0.30000000000000004
  console.log(sum==0.3);//false,js语言本身的bug
  ```

### String

字符串类型，值一般用单引号或双引号括起来。

- 字符串长度

  length属性用来获取字符串的长度

  ```javascript
  var str = 'Hello World';
  console.log(str.length);
  ```

- 字符串拼接

  字符串拼接使用 + 连接

  ```javascript
  console.log(11 + 11);
  console.log('hello' + ' world');
  console.log('100' + '100');
  console.log('11' + 11);
  console.log('male:' + true);
  ```

  1. 两边只要有一个是字符串，那么+就是字符串拼接功能
  2. 两边如果都是数字，那么就是算术功能。

### Boolean

布尔类型，只有两个值，true(1)、false(0)。

### Null

空类型，值只有一个null，一个对象指向了空，此时赋值为null。要让变量为null，只能通过赋值。

### Undefined

未定义，值只有一个undefined

什么情况下结果是undefined？

1. 变量声明了，没有赋值，结果是undefined；
2. 函数没有明确返回值，如果接收了，结果也是undefined。

```javascript
var num;

console.log(num);//输出：undefined

console.log(num+10);//输出：NaN  //Not an Number 不是一个数字
```

如果一个变量的结果是undefined，和一个数字进行计算，结果是NaN，不是一个数字，也没有意义。

### Object

对象，后面讲。

### 如何获取变量的数据类型

使用`typeof`来获取。

语法：

`typeof 变量名` 

`typeof(变量名)` 

```javascript
  <script>
      var num=20;
      var str="hello!";
      var bol=true;
      var undef;
      var nul=null;
      var obj=new Object();
      console.log(typeof num);//number
      console.log(typeof str);//string
      console.log(typeof bol);//boolean
      console.log(typeof undef);//undefined
      console.log(typeof nul);//object,null是指一个对象指向了空，所以类型是对象。
      console.log(typeof obj);//object
  </script>
```

## 数据类型转换

### 转为数字类型

#### parseInt() 转为整数

```javascript
var num1 = parseInt("12.3abc");  // 返回12，如果第一个字符是数字会解析知道遇到非数字结束
var num2 = parseInt("abc123");   // 返回NaN，如果第一个字符不是数字或者符号就返回NaN
```

#### parseFloat() 转为小数

```javascript
console.log(parseFloat("10"));//10
console.log(parseFloat("10.98.11"));//10.98
console.log(parseFloat("10.98edef"));//10.98
console.log(parseFloat("109385ggg"));//109385
console.log(parseFloat("fds10.1ggg"));//NaN
```

`parseFloat`会解析第一个`. `遇到第二个`.`或者非数字结束如果解析的内容里只有整数，解析成整数。

#### Number() 转为数字

```javascript
console.log(Number("10"));//10
console.log(Number("10.121"));//10.121
console.log(Number("10.98.11"));//NaN
console.log(Number("10.98edef"));//NaN
console.log(Number("109385ggg"));//NaN
console.log(Number("fds10.1ggg"));//NaN
```

比上两种方式严格

### 转为字符串类型

#### .toString()

```javascript
var num=10;
console.log(num.toString());//10
```

#### String()

```javascript
var num=10;
console.log(String(num));//10
```

区别：

如果变量有意义，使用`.toString()`转换；

如果变量没有意义，如null、undefined，使用`string()`转换，使用`.toString()`会报错。

一般来说，不会转没有意义的变量，所以主要用`.toString()`，为了保险可以用`.toString()`。

### 转为布尔类型

#### Boolean();

```javascript
console.log(Boolean(1));//true,非0数字都是true
console.log(Boolean(0));//false
console.log(Boolean(11));//true
console.log(Boolean(-11));//true
console.log(Boolean("hello"));//true,非空字符串也是true
console.log(Boolean(""));//false,空字符串是false
console.log(Boolean(null));//false,没有意义的是false
console.log(Boolean(undefined));//false,没有意义的是false
```

## 操作符

### 算数运算符

`+、-、*、/、%`

- 算数运算表达式

由算术运算符连接起来的表达式

### 一元运算符

只需要一个操作数就可以运算的符号` ++、--`

` ++`可以分为前`++`和后`++`

` --`可以分为前` --`和后` --`

如果没有参与运算，在前在后结果都一样。

num++ +10; //++在后，如果参与运算，先运算，再自身加1

++num +10; //++在前，如果参与运算，先自身加1，再运算

### 二元运算符

只需要两个操作数就可以运算的符号

### 三元运算符

只需要三个操作数就可以运算的符号

### 复合运算符（赋值运算符）

`+=、-=、*=、/=、%=`

- 复合运算表达式

由复合运算符连接的表达式

### 关系运算符

`>、<、>=、 <=、 ==(不严格，比较值)、===(严格，判断类型和值)、!=、!==`

- 关系运算表达式

由关系运算符连接的表达式，值是true或false

### 逻辑运算符

&&——逻辑与——>并且

|| ——逻辑或——>或者

！ ——逻辑非——>取反

- 逻辑运算表达式

由逻辑运算符连接的表达式。

`表达式1&&表达式2` 如果有1个表达式为false，则为false，两个表达式为ture才为true

`表达式1||表达式2` 如果一个表达式为true，则为true，两个表达式都为false才为false

`!表达式1` 如果表达式1为ture，则为false，如果表达式1为false，则为true

### 运算符的优先级

优先级从高到低：

  		1. ()  优先级最高
  		2. 一元运算符  ++   --   !
  		3. 算数运算符  先*  /  %   后 +   -
  		4. 关系运算符  >   >=   <   <=
  		5. 相等运算符   ==   !=    ===    !==
  		6. 逻辑运算符 先&&   后||
  		7. 赋值运算符

例：

`4 >= 6 || '人' != '阿凡达' && !(12 * 2 == 144) && true`

`false || true && true && true && true`——>true

## 表达式和语句 

### 表达式

>一个表达式可以产生一个值，有可能是运算、函数调用、有可能是字面量。表达式可以放在任何需要值的地方。

### 语句

>语句可以理解为一个行为，循环语句和判断语句就是典型的语句。一个程序有很多个语句组成，一般情况下;分割一个一个的语句。

## 流程控制

>程序的三种基本结构

### 顺序结构

 从上到下执行的代码就是顺序结构

**程序默认就是由上到下顺序执行的**

### 分支结构	

根据不同的情况，执行对应代码

### 循环结构

循环结构：重复做一件事情

## 分支结构

### if语句

语法结构

```javascript
//第一种
if (/* 条件表达式 */) {
  // 执行语句
}

//第二种
if (/* 条件表达式 */){
  // 成立执行语句
} else {
  // 否则执行语句
}

//第三种
if (/* 条件1 */){
  // 成立执行语句
} else if (/* 条件2 */){
  // 成立执行语句
} else if (/* 条件3 */){
  // 成立执行语句
} else {
  // 最后默认执行语句
}
```

### 三元运算符
	表达式1 ? 表达式2 : 表达式3

是对if……else语句的一种简化写法。

```javascript
var num=prompt("请输入一个数：");
var pri=num%2==0?"这是一个偶数":"这是一个奇数";
console.log(pri);
```

### switch语句

语法格式:
```javascript
switch (expression) {
  case 常量1:
    语句;
    break;
  case 常量2:
    语句;
    break;
  case 常量3:
    语句;
    break;
  …
  case 常量n:
    语句;
    break;
  default:
    语句;
    break;
}
```
break可以省略，如果省略，代码会继续执行下一个case
switch 语句在比较值时使用的是全等操作符, 因此不会发生类型转换（例如，字符串'10' 不等于数值 10）



## 循环结构

> 在javascript中，循环语句有三种，while、do..while、for循环。

### while语句

基本语法：

```javascript
// 当循环条件为true时，执行循环体，
// 当循环条件为false时，结束循环。
while (循环条件) {
  //循环体
  //计数器++
}
```

代码示例：

```javascript
// 计算1-100之间所有数的和
// 初始化变量
var i = 1;
var sum = 0;
// 判断条件
while (i <= 100) {
  // 循环体
  sum += i;
  // 自增
  i++;
}
console.log(sum);
```

### do...while语句

> do..while循环和while循环非常像，二者经常可以相互替代，但是do..while的特点是不管条件成不成立，都会执行一次。

基础语法：

```javascript
do {
  // 循环体;
  //计数器++
} while (循环条件);
```

代码示例：

```javascript
// 初始化变量
var i = 1;
var sum = 0;
do {
  sum += i;//循环体
  i++;//自增
} while (i <= 100);//循环条件
```

### for语句

>  while和do...while一般用来解决无法确认次数的循环。for循环一般在循环次数确定的时候比较方便

for循环语法：

```javascript
// for循环的表达式之间用的是;号分隔的，千万不要写成,
for (初始化表达式1; 判断表达式2; 自增表达式3) {
  // 循环体4
}
```

执行顺序：1243  ----  243   -----243(直到循环条件变成false)

1. 初始化表达式
2. 判断表达式
3. 自增表达式
4. 循环体

案例：

```
打印1-100之间所有数
求1-100之间所有数的和
求1-100之间所有数的平均值
求1-100之间所有偶数的和
同时求1-100之间所有偶数和奇数的和
打印正方形
// 使用拼字符串的方法的原因
// console.log 输出重复内容的问题
// console.log 默认输出内容介绍后有换行
var start = '';
for (var i = 0; i < 10; i++) {
  for (var j = 0; j < 10; j++) {
    start += '* ';
  }
  start += '\n';
}
console.log(start);
打印直角三角形
var start = '';
for (var i = 0; i < 10; i++) {
  for (var j = i; j < 10; j++) {
    start += '* ';
  }
  start += '\n';
}
console.log(start);

打印9*9乘法表
var str = '';
for (var i = 1; i <= 9; i++) {
  for (var j = i; j <=9; j++) {
    str += i + ' * ' + j + ' = ' + i * j + '\t';
  }
  str += '\n';
}
console.log(str);
```

作业：

```
求1-100之间所有数的乘积
求1-100之间所有奇数的和
计算1-100之间能3整除的数的和
计算1-100之间不能被7整除的数的和
// 讲解思路。如果不会写程序，可以先把数学公式准备好
本金10000元存入银行，年利率是千分之三，每过1年，将本金和利息相加作为新的本金。计算5年后，获得的本金是多少？
有个人想知道，一年之内一对兔子能繁殖多少对？于是就筑了一道围墙把一对兔子关在里面。已知一对兔子每个月可以生一对小兔子，而一对兔子从出生后第3个月起每月生一对小兔子。假如一年内没有发生死亡现象，那么，一对兔子一年内（12个月）能繁殖成多少对？（兔子的规律为数列，1，1，2，3，5，8，13，21）
```


### continue和break

> break:立即跳出整个循环，即循环结束，开始执行循环后面的内容（直接跳到大括号）
>
> continue:立即跳出当前循环，继续下一次循环（跳到i++的地方）

案例：

```javascript
求整数1～100的累加值，但要求碰到个位为3的数则停止累加
求整数1～100的累加值，但要求跳过所有个位为3的数
```

作业：

求1-100之间不能被7整除的整数的和（用continue）
求200-300之间所有的奇数的和（用continue）
求200-300之间第一个能被7整数的数（break）