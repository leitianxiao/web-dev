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

|知识点 |说明|
|---|---|
|通栏的盒子|不用给高度，默认|
|盒子居中对齐||
|行高会继承||



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

|浏览器	|MP3	|Wav	|Ogg|
|----|----|----|----|
|InternetExplorer	|YES|	NO|	NO|
|Chrome	|YES|	YES|	YES|
|Firefox	|YES|	YES	|YES|
|Safari	|YES|	YES|	NO|
|Opera|YES|YES	|YES|

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

|属性	|描述|
|----|----|
|transition|	简写属性，用于在一个属性中设置四个过渡属性。|
|transition-property|	规定应用过渡的 CSS 属性的名称。|
|transition-duration	|定义过渡效果花费的时间。默认是 0。|
|transition-timing-function	|规定过渡效果的时间曲线。默认是 "ease"。	|
|transition-delay|	规定过渡效果何时开始。默认是 0。|

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

|浏览器前缀|浏览器|
|----|---|
|-webkit-|google chrome,safari,Android browser|
|-moz-|firefox|
|-o-|opera|
|-ms-|IE,Edge|
|-kthml-|Kongqueror|

##### 动画animation
是CSS3具有颠覆性的特征之一。可以通过设置多个节点来精确控制一个或一组动画。可以在网页中取代动画图片、flash动画和javascript。
`animation:动画名称 花费时间 运动曲线 开始时间 播放次数 是否反方向`

animation是简写，用于设置六个动画属性：

|名称||
|----|---|
|animation-name	|规定需要绑定到选择器的 keyframe 名称|
|animation-duration|	规定完成动画所花费的时间，以秒或毫秒计。默认是0|
|animation-timing-function|	规定动画的速度曲线。默认ease|
|animation-delay|	规定在动画开始之前的延迟。默认是0|
|animation-iteration-count|	规定动画应该播放的次数。默认是1，n表示次数，infinite表示动画应该无限次播放|
|animation-direction|	规定是否应该轮流反向播放动画。默认是normal,alternate是轮流反向播放|
|animation-paly-state|规定动画是否正在运行或暂停，默认是running，paused暂停|
|animation-fill-mode|规定对象动画时间之外的状态|

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
|值|描述|
|---|---|
|h-shadow|必需，允许负值|
|v-shadow|必需，允许负值|
|blur|可选，模糊距离|
|color|可选，阴影颜色|

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

|属性值 |描述|
|---|---|
|length|设置背景图像的高度和宽度，如果只设定一个值，第二个值会被设置为auto|
|percentage|以父元素的百分比来设置背景图像的宽度和高度|
|cover|把背景图像扩展到足够大，以使背景图像完全覆盖背景区域|
|contain|把图像扩展到最大尺寸，以使其宽度和高度完全适应内容区域|


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



