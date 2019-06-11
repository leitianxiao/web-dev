### html/css

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
​	font-family:"iconfont";
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

|名称|说明|
|:---|:---|
|css|存放css文件|
|images|存放图片|
|index|京东首页html|
|fonts|存放字体图标|
|js|后期存放js文件 |



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









