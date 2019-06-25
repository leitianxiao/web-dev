## html/css



#### 开发工具

- sublime
- vs code
- webstorm

#### 浏览器内核

- Trident(IE内核)
- Gecko(Firefox内核)
- Webkit(Safari内核,Chrome内核原型,开源)
- Chromium/Blink(chrome内核)
- Presto(Opera前内核) (已废弃)

#### web标准
##### 网页组成
###### 结构（Structure) ——html

###### 表现（Presentation）——css

###### 行为（Behavior）——js

#### html骨架

```html
<html>
	<head>
	</head>
	<body>
	</body>
</html>
```

#### 标签关系

##### 嵌套关系
html-head

##### 并列关系

head-body

#### 文档类型、字符集

##### 文档类型

`<!DOCTYPE html>` html5的声明

##### 字符集

`<meta charset="utf-8">`

##### 其他字符集

###### GB2313

	简单中文，包括6763个汉字
###### GBK

	全部中文字符，是GB2313的扩展，加入对繁体字的支持
###### BIG5

	繁体中文，港澳台使用


#### 排版标签
##### 标题标签
`<h1>`-`<h6>`
##### 段落标签
`<p>`
##### 水平线标签
`<hr />`
##### 换行标签
`<br />`

#### div span
##### div
division-分区、分块

无语义、换行

##### span

跨度、不换行

#### 文本格式化标签
##### 加粗
`<b>`

`<strong>` 强调
##### 斜体
`<i>`

`<em>`
##### 加删除线
`<s>`

`<del>`
##### 加下划线
`<u>`

`<ins>`

#### 图像标签

`<img />`

###### 属性

`scr` 图像路径

`alt`	图片不显示时的文本

`title` 鼠标悬停时内容

`width`

`height`

`border` 图像边框宽度

#### 链接标签

`<a> </a>`

###### 属性

`href` 链接目标的地址

外部链接:http://www.baidu.com

内部链接:index.html

暂时不确定:#

`target` 窗口弹出的方式

self 当前窗口打开,默认

_blank 新窗口打开

#### 锚点标签

`<a href="#live">文本</a>` 目标元素如p
`<p id="live"></p>`

#### base标签

统一设置链接打开的状态
```
<head>
	<base target="_blank">
</head>
```

#### 特殊字符
空格符 `&nbsp;`

大于 `&lt;`

小于 `&gt;`

人民币 `&yen;`

版权 `&copy;`

注册商标 `&reg;`

乘号 `&times;`

除号 `&divide;`

平方 `&sup2;`

立方 `&sup3;`

#### 注释标签

`<!-- 注释内容 -->`

#### 路径

##### 相对路径
1.同一级 | 直接写文件名

2.下一级 | 上一级/文件名 | 一个/ 表示一级

3.上一级 | ../文件名 | 一个../ 表示一级

##### 绝对路径
从根目录开始 不建议使用

网络图片的url

#### 列表标签

##### 无序列表
```
<ul>
	<li>列表项1</li>
	<li>列表项2</li>
</ul>
```

##### 有序列表
```
<ol>
	<li>列表项1</li>
	<li>列表项2</li>
</ol>
```
##### 自定义列表
```
<dl>
	<dt></dt>
	<dd></dd>
	<dd></dd>
	<dt></dt>
	<dd></dd>
	<dd></dd>
</dl>
```


#### 表格table
##### 作用
布局 (现在不用了)

处理、显示表格式数据

##### 学习要求
1.手写表格结构
`<table>`

`<tr>`  行,一行可以有多列

`<td>` 列

2.合并单元格

##### 格式语法
```
<table>
	<tr>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
	</tr>
</table>
```
##### 属性
`width`

`height`

`border`

`align` 元素的水平对齐方式

`cellspacing` 单元格与单元格边框之间的空白距离

`cellpadding` 单元格内容与单元格边框之间的空白距离

业内常用，三参为0：`border` `cellspacing` `cellpadding`

##### 表格标题/表头单元格
###### 表头单元格
1.表头标签: `<th>`替代`<td>` ,自动加粗、居中

2.表格标题`<caption>`:
```
<table>
	<caption>标题</caption>
	<tr>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
	</tr>
</table>
```

##### 合并单元格
`rowspan` 跨列合并

`colspan` 跨行合并

`<td>`属性，从左到右，从上到下

##### 下拉菜单和文本域
###### label标签
1.为 input 元素定义标注（标记）

当用户选择该标签时，浏览器就会自动将焦点转到和标签相关的表单控件上。

2.`<label>用户名：<input type="text"><br></label>`

3.for属性

规定了label与哪个表单元素绑定

```
<label for="username">用户名：</label>
<input type="text" id="username">
```

###### textarea控件(文本域)
`text` 只能写一行文本

`textarea` 多行文本

属性:
`width`

`height`

`cols`文本域的列数

`rows` 文本域的行数


###### 下拉菜单
```
<select>
	<option>下拉选项1</option>
	<option>下拉选项2</option>
</select>
```
默认选中:`selected="selected"`
```
<option>下拉选项1</option>
<option selected="selected">下拉选项2</option>
```

###### 总结表格
1.表格提供了HTML中定义表格式数据的方法

2.表格中由行中的单元格组成

3.表格中没有列元素，列的个数取决于行的单元格格式

4.表格不要纠结与外观，那是css的事情

#### 表单标签

##### 目的

收集用户信息

##### 组成

###### 表单控件
表单元素`<input />`

属性
`type`：

- `text`

- `password`

- `radio` 单选框,一组单选项要有同一个name才可以单选

- `checkbox` 复选框

- `button` 普通按钮

- `submit` 提交按钮

- `reset` 重置按钮

- `image` 图像形式的提交按钮

- `file` 文件域


`name` 控件名称

`value` 默认文本值

`size` input控件在页面的显示宽度

`checked` 定义控件默认选项

`maxlength` 允许输入的最大字符数

###### 提示信息

###### 表单域
标签`<form>`

属性:
`action` 制定接收并处理表单数据的服务器程序的url地址

`method` 表单提交方式，
`post`不显示在地址栏
`get`显示在地址栏

`name` 表单名字

#### 查阅文档

http://www.w3school.com.cn/

https://developer.mozilla.org/zh-CN/

#### CSS

(Cascading Style Sheets 层叠样式表（级联样式表））

##### 作用

设置HTML页面的文本内容、图片外形、版面布局等外观样式

##### 引入css的位置

###### 内部样式表

CSS代码集中写在<head></head>里

```
<style>
	选择器{
		属性1:属性值1；属性2：属性值2；
	}
</style>
```
###### 行内式（内联样式）

```
<标签名 style="属性1":“属性值1”；"属性2:“属性值2”> 内容</标签名>
```

style是HTML所有标签都具备的属性，用来设置行内式

不适合大批量使用，偶尔也用

###### 外部样式表（外链式）

CSS代码集中写在单独的.css文件中，在HTML<head>中使用<link>链接

`test.css`
```
div{
    color: pink;
}
```
`test.html`
```
<head>
	<link rel="stylesheet" href="test.css">
</head>
```
`rel`属性，定义当前文档与链接文档之间的关系,stylesheet表示样式表文件

##### 三种样式表总结

1.行内样式表

书写方便，权重高；没有实现样式和结构分离；使用情况较少；最多控制一个标签

2.内部样式表

部分结构和样式分离；分离不彻底；使用情况较多；最多控制一个页面

3.外部样式表

实现结构和样式完全分离；需要引入；使用情况最多，强烈推荐；最多控制整个站点

##### 选择器

###### 目标

选择标签用

###### 基础选择器

- 标签选择器(把某一类标签全部选出来)

```
标签名{
	属性1:属性值1；属性2：属性值2；
}
```
- 类选择器(把某一class值相同的全部选出来)

命名规则:web前端开发规范手册

口诀:上面点开头，下面class调用
```							
.类名{
	属性1:属性值1；属性2：属性值2；
}
```
- 多类名选择器(给标签制定多个类名，从而达到更多的选择目的)

`<span class="blue red">内容<span>`
该span有两个类名，一个叫blue，一个叫red.

```
.blue{
	属性1:属性值1；
}
.red{
	属性2：属性值2；
}
```
span会拥有两个效果

- id选择器

```						
#id名{
	属性1:属性值1；属性2：属性值2；
}
```

- 与类选择器的区别

W3C标准规定，在同一个页面，不允许出现相同的id对象，但是允许相同名字的class

- 通配符选择器

```
*{
	属性1:属性值1；属性2：属性值2；
}
```

`*` HTML所有元素,实际开发中很少使用



#### CSS字体样式属性
##### font-size 字号大小
单位：

1.px 推荐使用

2.em

##### font-family 字体
1.使用英文 `font-family:"Microsoft YaHei"`

2.使用中文 `font-family:"微软雅黑"`

3.使用unicode编码  `font-family:"\5FAE\8F6F\96C5\9ED1"`

4.技巧

在网页中普遍使用14px+

尽量使用偶数的数字字号，ie6等老式浏览器支持奇数会有bug

各种字体之间必须用英文的逗号隔开

中文字体需要加引号，英文字体一般不需要加引号，当需要设置英文字体时，英文

字体名必须位于中文字体名之前

如果字体名包含空格、#、$等符号，则该字体必须加引号

尽量使用系统默认字体，保证在任何用户的浏览器都能正确显示


##### font-weight 字体粗细

###### 属性值

normal/regular 正常字体，等同于400

bold 粗体，等同于700

bolder 特粗体

lighter 细体

100-900（100的整数倍）

###### 语义标签
strong

b

##### font-style 字体风格

###### 属性值
normal 标准字体样式

italic 斜体的字体样式

oblique 倾斜的字体样式，没有斜体的字体，使用它来实现斜体

###### 语义标签
em

i

###### 技巧 

很少给文字加斜体，更常用标签<em><i>改为普通模式

##### font 综合设置字体样式

###### 格式

```html
选择器{
	font:font-style  font-weight  font-size/line-height  font-family;
}
```

必须按顺序书写，用空格隔开，不需要设置的属性可以省略，但必须保留font-size和font-family属性

#### CSS外观属性

##### color 文本颜色

###### 取值方式
1.预定义颜色值 red、green、blue

2.十六进制 `#FF0000` `#红红绿绿蓝蓝`

3.RGB代码 rgb（255,0,0）/rgb（100%，0%，0%）

##### line-height 行间距
行与行的距离，字符的垂直间距

###### 技巧
1.使用px单位

2.一般比字号大7-8px左右

##### text-align 水平对齐方式


###### 文本内容的水平对齐方式

重点是文字

`<h1>“水花兄弟”拒绝抢七！</h1>`

h1还是占一行，是h1中的文本对齐方式

###### css没有垂直对齐方式

###### 属性值

left

right

center
			

##### text-indent 首行缩进

一般用于中文中每个段落首行缩进2个字符

```						
p{ 
		text-indent: 2em;
 }
```

1em为一个中文字符
			

##### text-decoration 文本的装饰

###### 属性值
none 无装饰，取消装饰，可以与`<s>`标签搭配使用

underline 下划线

blink 闪烁 一般不使用

overline 上划线

line-through 贯穿线、删除线

###### 文本修饰标签总结

em i

取消倾斜 font-style:normal

添加倾斜 font-style:intalic

strong b 

取消加粗 font-weight:400

添加加粗 font-weight:700

u ins

取消下划线 text-decoration:none

添加下划线 text-decoration:underline

s del

取消删除线 text-decoration:none

添加删除线 text-decoration:line-throught

#### 调试工具

##### chrome浏览器

###### 呼出方式
右键"检查"

快捷键F12

###### 检查思路

1.选中有问题的元素

2.先检查结构 Elements

3.再检查样式 Styles

4.利用编辑器提示

5.技巧

加了删除线的表示没有生效

错误的地方有三角警告符号

后面是发生错误的代码行

可以直接双击修改属性和属性值查看效果，再去代码上直接修改

#### 复合选择器

##### 后代和子代选择器

###### 后代选择器（包含选择器）

目的：用来选择元素或元素组的后代，当标签发生嵌套时，内层标签就是外层标签的后代

语法：	

	外层选择器  内层选择器{
		属性1:属性值1；属性2：属性值2；	
	}	

##### 子代选择器
目的：不希望选择任意的后代元素，而是希望缩小范围，只选择某个元素的子元素

语法

```
外层选择器 > 子元素选择器{
	属性1:属性值1；属性2：属性值2；
}
```

##### 并集和交集选择器

###### 交集选择器
语法,既是选择器1，有时选择器2的

```					
选择器1选择器2{
	属性1:属性值1；属性2：属性值2；
}						
```

###### 并集选择器
语法,选择器1，选择器2并集

```
选择器1,选择器2{
	属性1:属性值1；属性2：属性值2；
}
```

###### 伪类选择器

目的: 给某些选择器添加特殊效果

###### 链接伪类选择器
`:link` 未访问的链接

`:visited` 已访问的链接

`:hover` 鼠标移动到链接上

`:active`选定的链接，点击鼠标的那一刻的样子

###### 技巧

记忆 ：类是一个点 .demo；伪类两个点 ：link
顺序是lvha，最好不要颠倒，记忆 love hate，lv ha

#### 编辑器的快捷方式

生成标签 直接输入标签名 按tab键即可

生成多个相同标签 标签名`* `想要生成的个数 按tab键即可div`*`3

生成父子级关系的标签`>`  ul>li

生成兄弟级关系的标签`+` div+p

生成带有类名或者id名字的标签`标签名.类名` `标签名#id名`

#### 标签显示模式

##### display 块级元素(block-level)
###### 特点
独自占据一整行或多行，可以设置宽度、高度、对齐等属性

常用于网页布局和网页结构的构建

###### 常见块元素

 h1-h6、p、div、ul、ol、li
				

##### 行内元素/内联元素（inline-level）
###### 特点

不占有独立的区域，仅仅靠自身字体大小和图像尺寸来支撑结构，一般不可设置宽度、高度、对齐
						

和相邻行内元素在一行

高宽无效，但水平方向的padding、margin可以设置，垂直方向无效

默认宽度是它本身内容的宽度

行内元素只能容纳文本或者其他行内元素（a特殊）

只有文字才能组成段落，因此p里面不能放块级元素，同理还有h1-h6、dt，他们都是文字类的块级标签

链接里不能再放链接

###### 常见行内元素

a、span、i、em、del、s、ins、u、strong

##### 块级元素和行内元素的区别
###### 块级

总是从新行开始

高度、行高、外边距以及内边距都可以控制

宽度默认是容器的100%

可以容纳内联元素和其他块元素
					

###### 行内
和相邻的行内元素在一行

高宽无效，但水平方向的padding、margin可以设置，垂直方向无效

宽度默认是它内容本身的宽度

行内元素只能容纳文本或者其他行内元素

行内元素和行内块元素可以看做 文本

##### 行内块元素（inline-block）

###### 标签

img、input、td

跟行内元素一样，一行可以有好几个，但是之间有空隙

默认宽度是它本身内容的宽度

宽度、行高、外边距以及内边距都可以控制
				

##### 标签显示模式转换
###### 块级元素转行内元素 display:inline

###### 行内元素转块级元素 display: block;

###### 转化为行内块元素 display:inline-block;
#### 注意点

`<a>`标签里不能再放a标签

`<a>`标签能放块级元素



#### 书写规范

1.选择器与花括号之间一定有空格

```
.demo {

}
```

2.属性名和之后的冒号`:`之间不允许包含空格，`:`与属性值之前必须包含空格

3.当一个rule包含多个选择器时，每个选择器声明独占一行

4.选择器的层级目录应不大于3级，位置靠后的限定条件应尽可能精确

5.属性必须另取一行，属性的后面必须分号结尾

#### 行高

##### 概念
![](../../100 - Work | 工作/110 - Work -Src | 源 /line-height.png)

##### 最常用用法

让一行文本在盒子中垂直居中，文字的行高等于盒子的高度

##### 盒子的高度

上距离+下距离+内容高度

上距离=下距离时，没有给行高时，上距离和下距离为0，只有内容的高度

行高=盒子高度时，上距离等于下距离，内容高度=字体高度，所以垂直居中

#### css三大特性
##### 层叠性
###### 概念

层叠，多种css样式的叠加。

是浏览器处理冲突的一个能力，如果出现冲突，会按照css书写的顺序，以最后的样式为准

###### 口诀

就近原则，不冲突不层叠

##### 继承性
###### 概念
继承，css样式表时，子标签会继承父标签的某些样式，如文本颜色、字号

想要设置一个可继承的属性，将它写在父元素中即可

###### 可继承的样式
text-

font-

line-

color属性

###### 口诀
子承父业

##### 优先级
###### 概念

优先级，css样式时，经常有2个或更多规则应用在同一元素上，这时，出现优先级问题

###### 权重
- 元素选择器  0,0,0,1

- 类、伪类选择器 0,0,1,0

- id选择器 0,1,0,0

- 行内样式表 1,0,0,0

- ！important 无穷大 最大

```
	选择器 {
属性1：属性值1！important
}
```

- `* `（选择器）/继承 0,0,0,0 最低

###### 技巧

1.权重相同时，就近原则

2.权重会叠加

- p (0,0,0,1)

- div>p (0,0,0,1+0,0,0,1=0,0,0,2)

3.继承的权重是0 (就算加了！important还是0)


#### css背景
##### 概念

css可以添加背景颜色和背景图片，以及进行图片设置
##### 属性

###### 背景颜色 background-color
###### 背景图片 background-image
###### 是否平铺 background-repeat
属性值

`repeat` 默认

`no-repeat`

`repeat-x` 水平方向上平铺

`repeat-y` 垂直方向上平铺

###### 背景位置 background-position
属性值 x y

- 1.方位名词:

`center` 居中

`top`

`bottom`

`left`

`right`

- 2.像素

- 3.百分比

使用


在一个盒子中，如果使用<img>标签，很难控制图片的位置，可以已背景图片的形式，通过background-position去控制位置

技巧

position后面可以跟方位名次，他们之间没有前后顺序

position如果只写一个方位名次，另一个方位默认居中

###### 背景固定或滚动 background-attachment
属性值

`fixed` 固定的(图片不随着滚轮滚动)

`scroll`滚动(默认值)

###### 背景的合写 backgroud

`backgroud：背景颜色 背景图片地址 背景平铺 背景滚动 背景位置`

###### 背景半透明

`background：rgba(r,g,b,a)`

red green blue（取值0-255） alpha(透明度，取值0-1)

#### 盒子模型
##### 组成
边框、内边距、外边距

##### 边框 border
###### border-width
###### border-style
`none` 没有边框,默认

`solid`实线边框

`dashed`虚线边框

`dotted`点线边框

###### border-color
###### border连写

border: border-width border-style border-color

`border:1px soild red;`

###### 边框拆分
border-top 上边框,<hr />效果可以用这个做

border-bottom 下边框

border-left

border-right

###### 表格细线边框

table的边框是指表格外面一圈，如果要表格行列都有边框，在tr上加border属性

###### 合并相邻边框
```
table {
	border-collapse:collapse;
}
```
##### 内边距 padding

边框与内容的之间的距离

###### padding-top 上内边距

###### padding-bottom 下内边距

###### padding-left

###### padding-right

###### 注意点

1.padding后面跟几个数值表示的意思不一样

1个值，上下左右内边距

2个值，上下内边距 左右内边距

3个值，上内边距 左右内边距 下内边距

4个值，上内边距 右内边距 下内边距 左内边距

2.padding会撑开带有width和height的盒子

##### 外边距 margin

元素与元素之间创建空白，这段空白不能放置其他内容

###### margin-top
###### margin-right
###### margin-left
###### margin-right
###### margin 上 右 下 左
取值顺序与padding相同


#### 盒子水平居中

###### text-align:center;

可以让盒子内容（文字、行内元素、行内块元素）居中对齐

###### margin:0 auto

盒子水平居中,最通俗的写法

###### margin-left:auto

左侧充满，盒子在最右侧

###### margin-right:auto

右侧充满，盒子在最左侧

###### 大厂盒子水平居中写法

`margin-left:auto;``margin-right:auto;`

###### margin:auto;

###### 原理

左右外边距都auto

###### 必要条件

必须是块级元素

盒子必须制定了宽度width

#### 插入图片和背景图片
##### 插入图片<img>

一般产品展示类用的插入图片

##### 背景图片<bgimage>

logo、小图标、超大的背景图片

#### css初始化、格式化

制作网页时，清除各元素的内外边距
```
*{
margin:0;
padding:0;
}
```
实际开发中，不用`*`，`*`代表所有，执行慢
```
body,ol,ul,h1,h2,h3,h4,h5,h6,p,th,td,dl,dd,form,fieldset,legend,input,textarea,select
{
margin:0;padding:0
}
```

#### 外边距合并

##### 相邻块元素垂直边距的合并（外边距的塌陷）

垂直间距不是两个盒子的margin值相加，而是以最大的margin值为准


##### 嵌套块元素垂直外边距的合并

两个嵌套关系的块元素，如果父元素没有内边距及边框，则父元素的上外边距会与子元素的上外边距发生合并，合并后的外边距为两者中的较大者，即使付款苏的上外边距为0，也会发生合并

###### 解决1
给父元素添加1px的上边框

给父元素添加1px的padding-top

缺点：增大了盒子，记得减去1px

###### 解决2

`overflow:hidden;` 超出隐藏

#### 盒子模型的总宽度和总高度计算原则
##### 外盒尺寸（元素空间尺寸）

element空间高度 =content height+padding+border+margin

element空间宽度 =content width+padding+border+margin
##### 内盒尺寸（元素实际大小）(常用)
element height =content height+padding+border

element width=content width+padding+border

##### 注意点

1.height width属性仅适用于块级元素，对行内元素无效

2.计算盒子模型的高度时，考虑上下两个盒子垂直外边距合并的情况

3.如果一个盒子没有给定宽度/高度或者继承父亲的宽度/高度，则padding不会影响盒子的大小

因为父元素给了宽度，所以会撑开盒子,子元素没有给宽度，所以不会撑开盒子

#### 盒子模型布局稳定性

##### 什么时候使用外边距、内边距

可混用，但按稳定性区分width>padding>margin

##### 原因

margin外边距合并

padding影响盒子大小，需要进行加减计算

width没有问题，常用宽度、高度剩余法

#### 圆角边框（CSS3）
##### 语法
###### 圆角矩形 border-radius: 5px;

###### 圆形
border-radius: 正方形边长的一半;

border-radius: 50%;

###### 单独赋值

`border-radius:1px 2px 10px 30px;` 左上角 右上角 右下角 右上角

##### css3存在兼容性问题

ie8以下不支持

#### 盒子阴影（css3）

##### 语法

box-shadow:水平阴影 垂直阴影 模糊距离 阴影尺寸 阴影颜色 内/外阴影

##### 属性值
###### h-shadow

必需，水平阴影位置，可负值

正值往右走

负值往左走

###### v-shadow
必需，垂直阴影的位置，可负值

正值往下走

负值往上走

###### blur

可选，模糊距离,虚实
###### spread

可选，阴影尺寸,阴影的大小
###### color

可选，阴影颜色
###### inset

可选，将外部阴影outset改为内部阴影

#### 浮动
##### 普通流/标准流（normal flow）
###### 模式

盒子单独占一行，添加一个盒子就自上而下的占第二行

行内元素，按顺序从左到右排列

##### 浮动（float）

元素的浮动是指设置了浮动属性的元素会脱离标准普通流的控制，移动到其父元素制定位置的过程,浮动就是不再占用原来的位置，由其他元素来占用

###### 属性值
`left`

`right`

`none`

`inherit`

应该从父元素继承 float 属性的值
##### 详细特性
1.脱标（脱离标准流），不占位置，会影响标准流，只有左右浮动，把浮动的元素加上父元素

2.浮动的元素总是想找他最近的父级元素对齐，但是不会超过内边距的距离

3.一个父盒子里有子盒子，如果其中一个子级有浮动，其他子级都需要浮动，这样才能一行显示

4.元素添加浮动后，元素会具有行内块元素的特性。元素的大小完全取决于定义的大小或者默认的内容多少

行内元素添加了浮动不需要转换也可以有宽高

块级元素添加了浮动，也具有行内块元素的特性

5.浮动的目的：为了让多个块级元素在同一行显示，核心是怎么排列，是否占位置

##### 总结
浮：加浮动让元素漂浮在元素的上面

漏：位置漏出来给底下的盒子

特：有自己的特性，需要与标准流的父级搭配使用，添加浮动，元素就有了行内块元素的特性

#### 版心与布局流程

##### 版心/可视区

是页面中主要内容所在的区域，一般指浏览器窗口水平居中显示，常见宽度值为960px、980px、1000px、1200px等

##### 布局流程

1.确定页面的版心（可视区）

2.分析页面中的行模块，以及每个行模块的列模块

3.制作HTML结构

4.CSS初始化，然后运用盒子模型的原理，通过div+css控制网页各个模块

##### 布局

###### 一列固定宽度且居中
top

banner

main

footer

###### 两列左窄右宽型
top

banner

left right

footer

###### 通栏平均分布型

top

banner

盒子  盒子  盒子  盒子

盒子  盒子  盒子  盒子

footer

#### 页面实战

##### 前期准备

###### 资源准备

1.images 图片文件夹

2.css css文件夹



###### 新建
1.index.html 首页

2.css/index.css 首页的css

###### 更改title
###### 引入css文件
`<link>`

#### 清除浮动

实际是清除浮动造成的影响

##### 为什么清除浮动

浮动元素不占用原文档流的位置，会对后面的元素排版产生影响，为了解决这些问题，此时需要在该元素中清除浮动

##### 清除浮动的本质

解决父级元素因为子级浮动引起内部高度为0的问题

##### 解决

1.清除浮动就是把浮动的盒子圈到里面，让父盒子闭合出口和入口不让他们出来影响其他元素

2.css中，clear属性用于清除浮动

```
选择器 {
	clear:属性值
}
```



`left` 清除左侧浮动影响

`right` 清除右侧浮动影响

`both` 同时清除两侧浮动影响

3.不是所有的浮动都需要清除，只清除对影响布局的浮动

##### 常用方法

###### 额外标签法
最后一个浮动标签的后面添加一个新标签，该标签添加clear属性

`<div class="clear" style="clear:both"></div>`

优缺点

通俗易懂，书写方便。添加很多无意义的标签，结构化差

###### 父级添加overflow属性方法
通过出发BFC的方法，给父级添加overflow，属性值：hidder、auto、scroll

优缺点

代码简洁，内容增多时，容易造成不会自动换行导致内容被隐藏掉，无法显示需要溢出的元素

###### 使用after伪元素清除浮动

正常浏览器
```
.clearfix:after {
content:"";
display:block;
height:0;
clear:both;
visibility:none;
}
```

ie6、7,其他浏览器不执行
```
.clearfix {
*zoom:1;
}
```

优缺点

符合闭合思想，结构语义化正确,由于IE6-7不支持：after，使用zoom：1触发hasLayout

###### 使用before和after双伪元素清除浮动
```
.clearfix:before,.clearfix:after {
content:"";
display:table;
}
.clearfix:after {
clear:both;
}
.clearfix {
*zoom:1;
}
```

优缺点

代码更简洁,由于IE6-7不支持：after，使用zoom：1触发hasLayout

#### 定位（position）

##### 定位属性

###### 定位模式
```
选择器 {
position:属性值；
}
```
属性值:
`static`  自动定位,默认

网页中所有元素都默认是静态定位，就是标准流的特性

唯一的用法就是取消定位

`relative`  相对定位

每次移动的位置是以左上角为基点移动（相对于自己来移动位置）

它通过偏移量移动位置，但是原来的所占位置继续占有

`absolute` 绝对定位

1.不占位置，跟浮动一样，脱标

2.没有父元素或父元素没有定位，以当前屏幕为基准点（ducument文档）

3.有父元素有定位，则根据最近的父元素（祖先）进行定位

4.子绝父相，子级用绝对定位的话，父级要用相对定位

理由：子级绝对定位不占有位置，不影响页面其他元素的位置；子级确定是绝对定位了，直接父级没有定位的话，子级元素会以屏幕为基准；如果父级是绝对定位，不占位置，后面的盒子会被影响，所以父级只能是相对定位

5.绝对定位的盒子居中对齐

加了定位和浮动的盒子，margin：0 auto失效

水平居中：首先left：50%，再设置margin-left:负的自己盒子的一半的值

垂直居中：top:50%,margin-top:负的自己盒子的一半

`fixed`  固定定位

绝对定位的一种特殊形式

它以浏览器窗口作为参照物，不管浏览器大小如何变化、滚动条如何滚动，都会显示在浏览器的固定位置

知识点

1.固定定位元素跟父元素没有任何关系，只认浏览器

2.固定定位完全脱标，不占有位置，不随着滚动条滚动

3.ie6等低版本浏览器不支持固定定位

###### 偏移量

top 顶端偏移量，定义元素相对于父元素上边线的距离

bottom 底部偏移量，定义元素相对于父元素下边线的距离

left 左侧偏移量，定义元素相对于父元素左边线的距离

right 右侧偏移量，定义元素相对于父元素右边线的距离

##### 知识点

加了定位和浮动的盒子，margin：0 auto失效

##### 定位模式转换

跟浮动一样，元素添加了绝对定位和固定定位之后，元素模式也会发生转换，都转为行内块模式

所以，如果添加了绝对定位或者固定定位或者浮动后，可以不用转换模式，直接给高度和宽度就可以

#### 叠放次序（z-index）

后来居上，都有定位的时候

要想调整重叠定位元素的堆叠顺序，可以对定位元素应用z-index层叠等级属性，取值为正整数、负整数和0

知识点
z-index的默认属性是0，取值越大，定位元素在层叠元素中居上

取值相同时，按书写书序，后来居上

后面数字一定不能加单位

只有相对定位、绝对定位、固定定位有此属性，其余标准流、浮动、静态定位都无此属性

#### 四种定位总结

| 定位模式         | 是否脱标，是否占位置 | 是否可使用边偏移 | 移动位置的基准                   |
| ---------------- | -------------------- | ---------------- | :------------------------------- |
| 静态定位static   | 不脱标，正常模式     | 不可以           | 正常模式                         |
| 相对定位relative | 脱标，占位置         | 可以             | 相对自身位置移动（自恋型）       |
| 绝对定位absolute | 完全脱标，不占有位置 | 可以             | 相对于定位父级移动位置（拼爹型） |
| 固定定位fixed    | 完全脱标，不占位置   | 可以             | 相对于浏览器移动位置（认死理型） |

#### 元素的显示与隐藏

##### display

属性值：

- none(隐藏)

- block(除了转换为块状元素之外，还有显示的意思)

特点：隐藏之后，不保留位置



##### visibility

属性值：

- visible（对象可视）

- inherit（继承父对象的可见性）

- hidden（对象隐藏）

特点：隐藏之后，保留位置



##### overflow

当内容溢出时发生的事。

属性值：

- visible（默认值。内容不会被修剪，会呈现在元素框之外。）

- auto（如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。）

- hidden（溢出隐藏）

- scroll（滚动）



#### CSS用户界面样式

##### 鼠标样式cursor

设置或检索在对象上移动鼠标指针采用何种系统预设定义的光标形状。

属性值：

- default（默认，箭头）
- pointer（小手）
- move（移动十字）
- text（文本）

##### 轮廓outline

绘制元素周围的一条线位于边框边缘外围，不是边框。

属性值：

- none （取消轮廓线）

- outline-color

- outline-style

- outline-width

##### 防止textarea拖拽

给textarea添加属性`resize:none;`

#### vertial-align垂直对齐

文字水平对齐：text-align

文字垂直对齐：line-height=行高

带有宽度的块级元素水平居中对齐：margin:0 auto;

vertial-align不影响块级元素中的内容对齐，它只针对行内元素和行内块元素，特别是行内块元素，通常用来控制图片/表单与文字的对齐。

属性值：

- baseline(默认，图片与文字基线对齐)
- middle(图片与文字的中线对齐)
- top(图片与文字的顶线对齐)

##### 去除图片底侧空白缝隙

vertial-align的一个特性：图片或者表单等行内元素，他的底线会和父级盒子的基线对齐。这样会造成图片底侧会有一个空白缝隙。

解决办法:

1. 不使用`vertial-align:baseline`，使用middle、top等，让图片不要和文字基线对齐。
2. 给img添加`display:block`转换为块级元素。

#### 溢出文字显示省略号

##### white-space

设置或检索对象内文本显示方式。通常我们使用于强制一行显示内容。

属性值：

- normal（自动换行）
- nowrap（强制在同一行内显示所有文本，知道文本结束或遇到br标签对象才换行）

#### text-overflow 文字溢出

设置或检索是否使用一个省略标记……标示对象内文本的溢出

属性值：

- clip（不显示省略号，而是简单裁切）
- ellipsis（当对象内文本溢出时显示省略标记……）

溢出文字显示省略号，需要三句话搭配使用：

```css
 {
	overflow: hidden;/*文字溢出时隐藏*/
	white-space: nowrap;/*强制在同一行显示所有文本*/
	text-overflow: ellipsis;/*溢出部分用省略号代替*/
}
```

#### CSS精灵技术（sprite）

##### 技术产生的背景

用户访问一个网站时，需要向服务器发送请求，网页上的每张图像都要经过一次请求才能展现给用户。一个网页中往往会有很多小的背景图作为修饰，当网页中的图像过多时，服务器会频繁的接受和发送请求，这将大大降低页面的加载速度，为了有效的减少服务器接受和发送请求的次数，提高页面加载速度，出现了CSS精灵技术。

##### 精灵技术的本质

css精灵是一种处理网页**背景图像**的方式，它将一个页面设计到的所有零星图像都集中到一张大图中去，然后将大图应用于网页，这样，当用户访问该页面时，只需要向服务器发送一次请求。网页中的背景图像即可全部展示出来。通常情况下，这个由很多小的背景图像合成大图被称为精灵图（雪碧图）。

##### 精灵图的使用

各个网页元素通常只需要精灵图中不同位置的某个小图，要想精确定位到精灵图中的某个小图，需要使用css的background-image、background-repeat、background-position属性进行背景定位。

`background: url(index.png) no-repeat 0px -218px;`

##### 制作精灵图

通过ps把多个小图做成大图，一般由美工完成。

小公司很少使用精灵图，维护成本高。

#### 滑动门

##### 滑动门出现的背景

制作网页时，为了美观，常常需要为网页元素设置特殊形状的背景，比如微信导航栏。

![img](https://images2018.cnblogs.com/blog/1310818/201805/1310818-20180512091727153-1635974458.png)

为了使各种特殊形状的背景能够自适应元素中文本内容的多少，出现了CSS滑动门技术。使各种特殊形状的背景能够自由拉伸滑动，以适应元素内部的文本内容，可用性更强。

##### 核心技术

![img](https://images2018.cnblogs.com/blog/1310818/201805/1310818-20180512093856424-267250876.png)

![img](https://images2018.cnblogs.com/blog/1310818/201805/1310818-20180512094430767-349816619.gif)

a>span

a 背景图像是左边切片

span 背景图像是右边切片，位置是靠右对齐

#### web字体

##### 字体格式

不同的浏览器所支持的字体格式是不一样的。我们先了解有关字体格式的知识。

1. TureType(.ttf)格式

   是win和mac最常见的字体，是一种RAW格式，支持这种字体的浏览器有IE9+、Firefox3.5+、Chrome4+、Safari3+、iOS Moblie、Safari4.2+

2. OpenType(.otf)格式

    被认为是一种原始的字体格式，其内置在TureType的基础上。

3. Web Open Font Format(.woff)格式

   是Web中的最佳格式，他是一个开放的TrueType/OpenType的压缩版本，同时也支持元数据包的分离

4. Embedded Open Type(.eot)格式

   IE专业字体，支持IE4+

5. SVG(.svg)格式

   基于SVG字体渲染的一种格式。

#### 字体图标

图片有诸多优点，但是缺点明显，比如图片不但增加了总文件的大小，还增加了很多额外的“http请求”，这都会大大降低网页的性能。更重要的是图片不能很好的进行“缩放”，因为图片放大和缩小会失真。字体图标（iconfont）能够满足这个需求。

##### 字体图标的优点

可以做图片可以做的事情，改变透明度、旋转度……

本质还是文字，可以随意改变颜色、产生阴影、透明效果

本身体积更小，但携带的信息并没有消减

几乎支持所有浏览器

移动端必备

##### 字体图标使用流程

1. UI人员设计字体图标效果图（svg）
2. 前端人员上传生成兼容性字体文件包
3. 前端人员下载兼容字体文件包到本地
4. 把字体文件包引入到HTML页面

###### 设计字体图标

假设图标是需要公司单独设计的，UI设计人员设计，存为.svg格式给到前端人员即可。

###### 上传生成字体包

设计人员给了.svg文件，上传到这些网站再转换为可使用的字体文件。

如果不需要单独设计，可在以下网站上进行选择、下载。

推荐网站：

icomoon : https://icomoon.io/

阿里巴巴Iconfont：https://www.iconfont.cn/  免费

fontello: <http://fontello.com/>  在线制定自己的字体图标，github开源项目

fontawesome :<http://fontawesome.dashgame.com/>> 更新比较快

###### 下载兼容字体包

下载到本地，放在项目的font文件夹下

###### 字体引入到HTML

第一步，在样式`<style>`中声明字体：告诉别人我们自己定义的字体

```css
@font-face {
    /* 1.首先指定字体的系列,我们指定为字体图标，可以自己取名 */
    font-family: "iconfont";
    /* 2.接下来的代码指定了字体图标的路径,兼容了各种移动端浏览器和PC端浏览器,你可以根据自己的需要,删除不必要的兼容 */
    src: url('iconfont.eot?t=1541904002925'); /* IE9*/
    src: url('iconfont.eot?t=1541904002925#iefix') format('embedded-opentype'), /* IE6-IE8 */
    url('iconfont.ttf?t=1541904002925') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
    url('iconfont.svg?t=1541904002925#iconfont') format('svg'); /* iOS 4.1- */
    font-weight:normal;
    font-style:normal;/* 倾斜字体变正常 */
}
```

第二步，`<span></span>`，复制demo中对应的字体图标到span元素

第三步，给盒子定义使用字体

```css
span {
	font-family:"iconfont";
}
```

##### 追加字体图标

工作中，原来的字体图标不够用需要新增字体图标，原来的不能删除，此时我们需要将压缩包中的selection.json重新上传，然后选中自己想要的新增图标，重新下载压缩包替换原来的文件。

#### 京东项目实战
……

##### 京东项目介绍
……

##### 项目背景

电商平台花样最多

##### 设计目标

保证浏览器兼容IE7以上，火狐、360、谷歌等
熟悉css+div布局，页面的搭建工作
了解常用电商的布局模式
为后期京东移动端做铺垫

##### 几点思考

###### 开发工具
sublime

###### CSS Reset类库

为跨浏览器兼容做准备（css初始化，清除浏览器自带的样式）

```
<!-京东css reset->
*{margin:0;padding:0}
em,i{font-style:normal}
li{list-style:none}
img{border:0;vertical-align:middle}
button{cursor:pointer}
a{color:#666;text-decoration:none}
a:hover{color:#e33333}
button,input{font-family:Microsoft YaHei,Heiti SC,tahoma,arial,Hiragino Sans GB,\\5B8B\4F53,sans-serif}
body{-webkit-font-smoothing:antialiased;background-color:#fff;font:12px/1.5 Microsoft YaHei,Heiti SC,tahoma,arial,Hiragino Sans GB,\\5B8B\4F53,sans-serif;color:#666}
.hide,.none{display:none}.clearfix:after{visibility:hidden;clear:both;display:block;content:".";height:0}.clearfix{*zoom:1}

```

说明：`font:12px/1.5 Microsoft YaHei` 字号12px，行高为字体大小的1.5倍）。

`Normalize.css`只是一个很小的css文件，但它在磨人的HTML元素样式上提供了跨浏览器的高度一致性。相比于传统的CSS reset,Normalize.css是一种现代的、为HTML5准备的优质替代方案。

获取normalize.css：
https://github.com/necolas/normalize.css 下载normalize.css文件

创造normalize.css有下面这几个目的：

保护有用的浏览器样式而不是去掉他们。

一般化的样式：为大部分HTML元素提供。

修复浏览器自身的bug并保证各浏览器的一致性。

优化css可用性：用一些小技巧。

解释代码：用注释和详细的文档来。

###### 技术栈
html+css布局

###### 低版本浏览器 ie6
单独做一个跳转页面

##### 目录说明
要实现结构和样式分离的设计思想，根目录下有这四个文件夹（目录）。

| 名称   | 说明           |
| :----- | :------------- |
| css    | 存放css文件    |
| images | 存放图片       |
| index  | 京东首页html   |
| fonts  | 存放字体图标   |
| js     | 后期存放js文件 |



##### 运用知识点
###### 引入ico图标

获取地址：https://www.jd.com/favicon.ico
几乎所有网站都是这样，在域名后加`/favicon.ico `

代码：
`<link rel="icon" href="favicon.ico" type="image/x-icon" />`


注意：

1.它不是iconfont，也是图片

2.位置是放在`<head>`标签中

3.后面的`type="image/x-icon"`可以省略

4.为了兼容性，请将favicon.ico这个图标放在根目录下

###### 转换ico图标
可以自己做图片，转为ico图标

###### 网站优化三大标签

SEO（Search Engine Optimization），搜索引擎优化。是指通过对网站进行站内优化（内容建设、网站代码优化等）和站外优化，提高网站的关键词排名以及产品曝光度。

前端开发主要进行站内优化。

三大标签：`title` `description` `keywords`

1.title 网站标题

不可替代性，搜索引擎入口。

- 标题的长度：

谷歌70kb 35个中文

百度56kb 28个中文

- 关键字分布：

越先出现的词语权重越高

- 关键字词频：

主关键字出现3次，辅关键字出现一次

- 建议：

首页标题 网站名（产品名）-网站介绍

例如：

京东(JD.COM)-正品低价、品质保障、配送及时、轻松购物！

小米商城 - 小米9、小米MIX 3、Redmi K20，小米电视官方网站

2.description 网站说明

搜索引擎中显示的简短说明。

![](../../100 - Work | 工作/110 - Work -Src | 源 /jddescription.png)

- 用法：

`<meta name="description" content="网站说明内容">`

- 注意点：

描述中的关键字是给人看的，要写得详细，让人感兴趣。

遵循简短原则，字符数含空格在内不要超过120个汉字。

补充title 和keyword中未能充分表述的说明。

用英文逗号 关键词1，关键词2

3.keywords 关键字

页面关键字，是搜索引起关注点之一，keywords应该在6-8个关键词左右

-用法：

`<meta name="keywords" content="关键词1,关键词2,……">`

##### 顶部快捷菜单栏所用知识点

| 知识点       | 说明             |
| ------------ | ---------------- |
| 通栏的盒子   | 不用给高度，默认 |
| 盒子居中对齐 |                  |
| 行高会继承   |                  |



##### CSS W3C 统一验证工具

cssstats 在线的css代码分析工具   

https://cssstats.com/

W3C 统一验证工具 支持本地文件

http://validator.w3.org/unicorn/

```
.clearfix {
  *zoom:1;
}
```

会认证不通过，因为高版本的浏览器不使用这种写法的。属于`css hack`,是用来解决低版本的浏览器问题。

##### 代码压缩

开发时，竖着书写，方便阅读。上线时，进行代码压缩，减少代码页面的时间。

推荐网站 ：http://www.chinaz.com/

很多功能跟前端有关系，比如SEO排名、搜索权重、CSS格式化（代码压缩）等……

注意：

压缩之后要保证代码能用

压缩之后起名叫 `xxx.min.css`

本地要保留原始文件，线上上传压缩文件。

#### html5 新标签与特性

IE9以上的版本才支持。除非针对这些属性再去找一些hack。

##### 文档类型设定

document:

HTML 输入html:4s

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```
XHTML 输入html:xl

HTML5 输入html5

`<!DOCTYPE html>`

##### 字符设定

HTML和XHTML中：

`<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />`

HTML5中：

`<meta charset="UTF-8">`

##### 常用新标签

w3c手册中文官网：http://www.w3school.com.cn/
html5 新内容：

http://www.w3school.com.cn/html5/html_5_intro.asp

- header 定义文档的页眉 头部

- nav 定义导航链接部分

- footer  定义文档或节的页脚 尾部

- article 定义文章

- section 定义文档中的节（section、区段）

- aside 定义其所处内容之外的内容 侧边

- datalist 标签定义选项列表 与input元素配合使用
```
<!-- input的list与datalist的id关联 -->
<input type="text" name="" id="" placeholder="请输入明星：" list="star">
<datalist id="star">
    <option value="刘德华">
    <option value="刘若英">
    <option value="戚薇">
</datalist>
```
option 元素永远都要设置 value 属性。

- fieldset 元素可将表单内的相关元素分组，打包 与legend搭配使用
```
<fieldset>
    <legend>用户信息</legend>
    用户名：<input type="text"><br>
    密码：<input type="password">
</fieldset>
```

#### 新增input type属性

- placeholder 占位符，当用户输入时，里面的文字消失，删除时，再出现。
```
<input type="text" name="" id="" placeholder="请输入数字：">
```

- autofocus 自动获得焦点，当页面加载时 input元素自动获得焦点
```
用户名：<input type="text" autofocus="autofocus">
```

- mulitple 多文件上传，`file`只能单选
```
<!-- 单文件上传 -->
<input type="file" name="" id="">
<!-- 多文件上传 按ctrl键多选 -->
<input type="file" name="" id="" multiple>
或
<input type="file" name="" id="" multiple="multiple">
```

- autocomplete 规定 `form` 或 `input` 域应该拥有自动完成功能

- required 必填项，内容不能为空
```
<input type="text" required="required">
或
<input type="text" required>
```
- accesskey 规定激活（使元素获得焦点）的快捷键
```
<input type="text" accesskey="s">
```
不同浏览器使用`s`或`alt+s`或`alt+shift+s`能让那个焦点落在该元素上。mac电脑使用`ctrl+alt+s`

##### 多媒体标签

- embed 标签定义嵌入的内容

- audio 播放音频

- video 播放视频

###### embed
embed可以用来插入各种多媒体，格式可以是 Midi、Wav、AIFF、AU、MP3等,url为音频或视频文件及其路径，可以是相对路径或绝对路径。
```
<embed height=498 width=510 src='http://player.youku.com/embed/XNDE0MTMwNTcxMg==' frameborder=0 'allowfullscreen'>
```
###### audio
HTML5通过`<audio>`标签来解决音频的播放问题。
```
<!-- 通过src指定音频文件的路径即可 -->
<audio src=“path.mp3”>

```

并可通过附加的属性来控制音频的播放：

`autoplay` 音频在就绪后马上播放。**(浏览器禁止autoplay？？？)**

`controls` 向用户显示音频控件（比如播放/暂停按钮）

`loop` 循环播放

`muted` 静音

当前，audio元素支持三种音频格式MP3、Wav、Ogg

推荐工具：格式工厂 ，可以转换为各种格式。

各浏览器对格式的支持情况：

| 浏览器           | MP3  | Wav  | Ogg  |
| ---------------- | ---- | ---- | ---- |
| InternetExplorer | YES  | NO   | NO   |
| Chrome           | YES  | YES  | YES  |
| Firefox          | YES  | YES  | YES  |
| Safari           | YES  | YES  | NO   |
| Opera            | YES  | YES  | YES  |

多浏览器支持的方案：
```
<audio  autoplay controls >
    <source src="deng.mp3" />
    <source src="deng.ogg" />
    <source src="deng.wav" />
    您的浏览器版本太低。
</audio>
```

###### video
HTML5使用`<video>`来解决音频问题。

用来控制视频的播放的属性

`autoplay` 自动播放

`controls` 向用户显示视频控件（比如播放/暂停按钮）

`loop` 循环播放

`muted` 静音

`width` 设置播放窗口的宽度

`height` 设置播放窗口的高度

video元素支持三种视频格式，Ogg、MPEG4、WebM

多浏览器支持的方案：
```
<video  autoplay controls >
    <source src="movie.mp4" />
    <source src="deng.ogg" />
    <source src="deng.wav" />
    您的浏览器版本太低。
</audio>
```

#### CSS3 新增选择器

##### 结构（位置）伪类选择器
- :first-child 选取属于其父元素的首个子元素的指定选择器
```
<!-- 第一个li的color为红色 -->
ul :first-child {
    color: red;
}
或
ul li:first-child {
    color: red;
}
```

- :last-child 选取属于其父元素的最后一个子元素的指定选择器

- :nth-child(n) 匹配属于其父元素的第N个子元素，无论元素类型
```
<!-- 第3个元素 -->
ul :nth-child(3) {
    background-color: pink;
}
<!-- 偶数个元素 -->
ul :nth-child(even) {
    background-color: pink;
}
<!-- 奇数个元素 -->
ul :nth-child(odd) {
    background-color: black;
}
<!-- 所有元素，n从0开始 -->
ul :nth-child(n) {
    background-color: black;
}
<!-- 偶数个元素 -->
ul :nth-child(2n) {
    background-color: black;
}
<!-- 奇数个元素 -->
ul :nth-child(2n+1) {
    background-color: black;
}
```
- :nth-last-child(n) 匹配属于其父元素的第N个子元素，无论元素类型，从最后

##### 属性选择器
根据元素的属性及属性值来选择元素
```
标签[属性] {
  ……
}
<!-- 选择有class属性的div -->
div[class] {
    background-color: pink;
}
<!-- 选择有id值为name的div -->
div[id=demo] {
    background-color: pink;
}
<!-- 选择class值以demo开头的div -->
div[class^=demo] {
    background-color: pink;
}
<!-- 选择class值以demo结尾的div -->
div[class$=demo] {
   background-color: yellow;
}
<!-- 选择class值包含demo的div -->
div[class*=demo] {
   background-color: yellow;
}
```

##### 伪元素选择器
1.E::first-letter 文本的第一个单词或字
2.E::first-line 文本第一行
3.E::selection 可改变选中文本的样式
4.before:: 在被选元素的内容前面插入内容，使用 content 属性来指定要插入的内容。

```
<!-- 插入的内容是在p标签的内部内容的前面 ，其实是个行内盒子  -->
p::before {
   content: "hello world";
}
```
5.after::  在被选元素的内容后面插入内容，使用 content 属性来指定要插入的内容。

##### CSS3盒模型
CSS3中可以通过box-sizing来指定盒模型，即可指定为content-box、border-box，这样我们计算盒子就可以分为两种情况：
//外加模式,CSS2中的盒子模型
1.box-sizing:content-box 盒子大小为width+padding+border content-box:此值为默认值
//内减模式
2.box-sizing:border-box 盒子大小为width 就是说padding和border是包含在width里的
注：上面标注的width指的是CSS属性里设置的width:length，content的值是会自动调整的。

###### 小米案例
鼠标经过时，原图内部增加一个透明边框效果
```
<style>
     * {
         margin:0;
         padding: 0;
     }
     div {
         width: 150px;
         height: 100px;

     }
     img {
         width: 100%;
         height: 100%;
     }
     <!-- 鼠标经过插入伪元素 -->
     div:hover::after {
         content: "";
         width: 150px;
         height: 100px;
         position: absolute;
         top: 0;
         left: 0;
         border:5px solid rgba(255, 255, 255, 0.5);
         <-- box-sizing 避免盒子被挤开 -->
         box-sizing: border-box;
     }
 </style>
 -----
 <body>
    <div>
        <img src="mycat.jpeg" alt="">
    </div>
</body>
```

##### 学成在线综合案例
###### 图片转换为ico图标
1.先切图 透明图片仅有gif和png格式支持
2.把图片转换为图标，在线转换网站 http://www.bitbug.net/

###### logo的写法
1.结构：div>a>h1、img
2.隐藏h1   `position: absolute;` `overflow: hidden;` `text-indent: -9999px;`

```
<!-- logo start -->
    <div class="logo">
        <a href="#" tiltle="学成在线">
            <h1>学成在线</h1>
            <img src="images/xclogo.png" alt="">
        </a>
    </div>
<!-- logo end -->
-----
<style>
    .logo {
        width: 170px;
        height: 35px;
        position: absolute;
        top: 50%;
        left: -170px;
        margin-top: -17px;
      }
    .logo img {
        width: 100%;
        height: 100%;
    }
    .logo a {
        display: block;
        width: 170px;
        height: 35px;
    }  
    .logo h1 {
        position: absolute;
        overflow: hidden;
        text-indent: -9999px;
    }
</style>

```
##### 过渡（CSS3）
过渡（transition）是css中具有颠覆性的特性之一。无需使用Flash动画或JavaScript，可以添加添加某种效果可以从一种样式转变到另一个。

过渡动画：是从一种状态渐渐过渡到另外一种状态。

帧动画：通过一帧一帧的画面按照固定顺序和速度播放。

`transition:要过渡的属性 过渡效果花费的时间 过渡效果的时间曲线 过渡效果开始的时间`

| 属性                       | 描述                                         |
| -------------------------- | -------------------------------------------- |
| transition                 | 简写属性，用于在一个属性中设置四个过渡属性。 |
| transition-property        | 规定应用过渡的 CSS 属性的名称。              |
| transition-duration        | 定义过渡效果花费的时间。默认是 0。           |
| transition-timing-function | 规定过渡效果的时间曲线。默认是 "ease"。      |
| transition-delay           | 规定过渡效果何时开始。默认是 0。             |

添加多个样式的变换效果，添加的属性由逗号分隔。

所有属性可以用all。

过渡最好写在本体上。

运动曲线：
linear  线性过渡

ease 平滑过渡

ease-in 由慢到快

ease-out 由快到慢

##### 2D变形（CSS3） transform
transform是CSS3具有颠覆性的特征之一，可以实现元素位移、旋转、倾斜、缩放，甚至支持矩阵。可以取代大量之前只能靠flash才可以实现的效果

###### 移动translate(x,y)

translate(x,y) 水平方向和垂直方向同时移动

translateX(X) 仅水平方向移动

translateY(Y) 仅垂直方向移动

```
<!-- 实现定位的盒子水平、垂直居中 -->
<!-- translate 如果x是50%，是跟父亲没有关系的，是走自己的50% -->
div {
    width: 100px;
    height: 100px;
    background-color: pink;
    position: absolute;
    top: 50%;
    left:50%;
    transform: translate(-50%,-50%);  
}

```

###### 缩放scale(x,y)

scale(x,y) 使元素水平方向和垂直方向同时缩放

scaleX(X) 元素仅水平方向缩放

scaleY(Y) 元素仅垂直方向缩放

`transform: scale(0.8,1);` 宽度变为原来的80%，高度不变。

`transform: scale(0.8);` 高度省略，默认和宽度一起缩放80%。

###### 旋转rotate(deg)

可以对元素进行旋转，正值为顺时针，负值为逆时针。
`transform:rotate(45deg);`


###### transform-origin可以调整元素转换变形的原点
```
<!-- 以右上角为原点，顺时针旋转30度 -->
div {
    transform-origin: right top;
    transform: rotate(30deg);
}
<!-- 以水平方向10px 垂直方向10px为原点，顺时针旋转30度 -->
div {
    transform-origin: 10px 10px;
    transform: rotate(30deg);
}
```
###### 倾斜 skew(deg,deg)
可以使元素按一定的角度进行倾斜，可以为负值，第二个参数不写默认为0；

`transform: skew(30deg,0deg);` 把元素水平方向向上倾斜30度，处置方向保持不变

主要做阴影效果。

##### 浏览器前缀
后面我们常用解决H5和C3的兼容解决文件，我们这里暂不涉及。

| 浏览器前缀 | 浏览器                               |
| ---------- | ------------------------------------ |
| -webkit-   | google chrome,safari,Android browser |
| -moz-      | firefox                              |
| -o-        | opera                                |
| -ms-       | IE,Edge                              |
| -kthml-    | Kongqueror                           |

##### 动画animation
是CSS3具有颠覆性的特征之一。可以通过设置多个节点来精确控制一个或一组动画。可以在网页中取代动画图片、flash动画和javascript。
`animation:动画名称 花费时间 运动曲线 开始时间 播放次数 是否反方向`

animation是简写，用于设置六个动画属性：

| 名称                      |                                                              |
| ------------------------- | ------------------------------------------------------------ |
| animation-name            | 规定需要绑定到选择器的 keyframe 名称                         |
| animation-duration        | 规定完成动画所花费的时间，以秒或毫秒计。默认是0              |
| animation-timing-function | 规定动画的速度曲线。默认ease                                 |
| animation-delay           | 规定在动画开始之前的延迟。默认是0                            |
| animation-iteration-count | 规定动画应该播放的次数。默认是1，n表示次数，infinite表示动画应该无限次播放 |
| animation-direction       | 规定是否应该轮流反向播放动画。默认是normal,alternate是轮流反向播放 |
| animation-paly-state      | 规定动画是否正在运行或暂停，默认是running，paused暂停        |
| animation-fill-mode       | 规定对象动画时间之外的状态                                   |

声明动画 `@keyframes` 关键帧,声明动画可以多方调用。

```
<style>
    div {
        width: 100px;
        height: 100px;
        background-color: pink;
        position: absolute;
        left: 0;
        /* 调用动画move */
        /* animation: name duration timing-function delay iteration-count direction fill-mode; */
        animation: move 3s ease 1s infinite;
    }
    /* 使用@keyframes声明动画,动画名称叫move */
    @keyframes move {
        from {  
            left: 0;
            background-color: red;
        }
        to {
            left: 100px;
            background-color: skyblue;
        }
    }
</style>
```

多个动作时可以使用
```
@keyframes move {
    0% {  

    }
    50% {

    }
    100% {

    }
}
```

##### 伸缩布局(flex)
Flex是Flexible Box的缩写，意为”弹性布局”。

###### 属性讲解

1.flex子项目在主轴上的缩放比例，不指定flex属性的不参与伸缩分配。
- display:flex；
- flex:1;
- min-width 最小宽度，即使弹性布局也不能无限压缩，通过该字段来规定盒子压缩的最小宽度,压缩到最小宽度时无法再压缩。
- max-width 最大宽度
- min-height
- max-height

2.flex-direction 调整主轴方向（默认为水平方向）
flex-direction:column; 垂直排列
flex-direction:row; 水平排列

##### 携程案例
https://m.ctrip.com/html5/

```
<style>
       * {
           margin: 0;
           padding: 0;
           box-sizing: border-box;
       }
       body {
           min-width: 320px;
           max-width: 500px;
           margin: 0 auto;
           background-color: #fff;
       }
       a {
           text-decoration: none;
           color: #fff;
       }
       header {
           height: 150px;
       }
       header img {
           height: 150px;
           width: 100%;
       }
       nav {
           border: 1px solid #cccccc;
           padding: 4px;
       }
       .row {
           height: 90px;
           display: flex;
           background-color: #ff6a7f;
           border-radius: 5px;
       }
       .row div {
           height: 100%;
           flex: 1;
           border-right:1px solid #fff;
       }
       .row div:nth-child(3) {
           border-right:none;
       }
       .row a {
           display: block;
           height: 100%;
           width: 100%;
           text-align: center;
           line-height: 45px;   
       }
       .row-33 {
           display: flex;
           flex-direction:column;
       }
       .row-33 a {
           flex:1;
           border-bottom: 1px solid #fff;
       }
       .row-33 a:nth-child(2) {
           border-bottom: none;
       }
   </style>
</head>
<body>
   <header>
       <img src="mtrip-banner.jpg" alt="">
   </header>
   <nav>
       <div class="row">
           <div>
               <a href="#">酒店</a>
               <i></i>
           </div>
           <div class="row-33">
               <a href="#">民俗</a>
               <a href="#">客栈</a>
           </div>
           <div class="row-33">
               <a href="#">公寓</a>
               <a href="#">宾馆</a>
           </div>
       </div>
   </nav>
</body>
```
##### 文字阴影
给文字添加阴影效果，区别与box-shadow。

`text-shadow:水平位置 垂直位置 模糊距离 阴影颜色。`
| 值       | 描述           |
| -------- | -------------- |
| h-shadow | 必需，允许负值 |
| v-shadow | 必需，允许负值 |
| blur     | 可选，模糊距离 |
| color    | 可选，阴影颜色 |

##### 背景渐变
仅讲线性渐变，颜色沿着一条直线过渡，从左到右、从右到左、从顶部到底部、从底部到顶部……

向下/向上/向左/向右/对角方向

兼容性问题很严重

1.linear-gradient 线性渐变

`background: linear-gradient(direction, color-stop1, color-stop2, ...);`

线性渐变至少两个颜色节点。

`background: linear-gradient(渐变起始位置, 颜色 位置, 颜色 位置，……);`

background: linear-gradient(top, red 0%, green 30%,blue 70%);

2.浏览器支持

需添加浏览器前缀,否则可能不显示。

```
#grad {
  background: -webkit-linear-gradient(red, blue); /* Safari 5.1 - 6.0 */
  background: -o-linear-gradient(red, blue); /* Opera 11.1 - 12.0 */
  background: -moz-linear-gradient(red, blue); /* Firefox 3.6 - 15 */
  background: linear-gradient(red, blue); /* 标准的语法 */
}
```
##### 背景缩放

通过background-size设置背景图片的尺寸，就像我们设置img尺寸一样。
应用：移动端，因为ios会放大像素，所以背景图同常按照尺寸的2倍来做，再进行缩放，才能保证高清。

其参数可以设置如下：

1.可以设置为长度单位px或百分比

2.设置为cover时会自动调整缩放比例，保证图片始终充满背景区域，如果溢出则隐藏

3.设置为contain会自动调整缩放比例，保证图片始终完整显示在背景区域

`background-size:length|percentage|cover|contain`

| 属性值     | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| length     | 设置背景图像的高度和宽度，如果只设定一个值，第二个值会被设置为auto |
| percentage | 以父元素的百分比来设置背景图像的宽度和高度                   |
| cover      | 把背景图像扩展到足够大，以使背景图像完全覆盖背景区域         |
| contain    | 把图像扩展到最大尺寸，以使其宽度和高度完全适应内容区域       |


##### 多背景

在一个盒子中设置多个背景图片。

使用逗号隔开，可以写多个url

`backgroud:url(1.jpg) no-repeat top left,url(2.jpg) no-repeat bottom  right;`



##### 盒子半透明

`background:rgba(255,0,0,.2)`  背景半透明，里面的内容不透明。



`opacity:0.2`  盒子半透明，里面的内容也透明。以前做的时候需要用`p`建立兄弟关系，通过定位做成背景半透明效果。

##### 优雅降级和渐进加强(根据客户需求)

渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高版本的浏览器进行效果、用户体验。



优雅降级：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。



建议：互联网发展快，连微软公司都抛弃IE浏览器，转而支持Edge，我们很多情况下没有必要再时刻想着低版本浏览器了，而是一开始就构建完整的效果，根据实际情况，修补低版本浏览器问题。

##### 3D变形（CSS3） transform

3d:x y z 



超炫的3d效果一般用js来实现。css进行一些简单的3d效果。



左手坐标系：大拇指与食指成L型，大拇指向右x+，食指向上y+，中指指向外z+，建立向x,y,z轴；



css的坐标方向与上述坐标方法刚好相反。相当于绕着x轴翻转180度。大拇指向右x+，食指向下y+，中指指向自己z+。



###### rotateX()

沿着X轴立体旋转。

`transform:rotateX(180deg);`



###### rotateY()

沿着Y轴立体旋转。



rotateZ()

沿着Z轴立体旋转。



##### 透视

电脑显示屏时一个2d平面，图像之所以具有立体感，其实是种视觉呈现。透视可以将一个2d平面，在转换过程中，呈现3d效果。

- 透视原理：近大远小。
- 浏览器透视：把近大远小的所有图像，透视在屏幕上。
- perspective：视距，表示视点距离屏幕的长短。视点，用于模拟透视效果时人眼的位置。

注：并非任何情况下需要透视效果，根据开发需要。



`perspective`  作为一个属性，设置给父元素，作用于所有3d转换的子元素。

`backface-visibility：hidden;` 不是正面对象屏幕就隐藏。