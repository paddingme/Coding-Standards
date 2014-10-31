
# 页面编码规范

## 通用约定

#### 文件与目录命名约定

1. 一律小写, 必须是英文单词或产品名称的拼音, 多个单词用连字符(-)连接. 只能出现英文字母、数字和连字符, 严禁出现中文.
2. 出现版本号时, 需要用字母 v 做为前缀, 小版本号用点号(.)隔开, 比如 global-v8.js 或 detail-v2.2.js .
3. 该命名规范适用于 html, css, js, swf, php, xml, png, gif, jpg, ico 等前端维护的所有文件类型和相关目录.
4. js 和 css 压缩文件, 统一以 -min 结尾, 比如源码文件为 seed.js, 压缩后为 seed-min.js

#### 文件编码约定

1. 使用 UTF-8 编码
2. 引入的第三方组件除外


#### id 和 class 命名约定

1. id 和 class 的命名总规则为：内容优先,表现为辅. 首先根据内容来命名, 比如 main-nav. 如果根据内容找不到合适的命名, 可以再结合表现来定, 比如 skin-blue, present-tab, col-main.
2. id 和 class 名称一律小写, 多个单词用连字符连接, 比如 recommend-presents.
3. id 和 class 名称中只能出现小写的 26 个英文字母、数字和连字符(-), 任何其它字符都严禁出现.
4. id 和 class 尽量用英文单词命名 . 确实找不到合适的单词时, 可以考虑使用产品的中文拼音, 比如 wangwang, dating. 对于中国以及淘宝特色词汇, 也可以使用拼音, 比如 xiaobao, daigou. 除了产品名称和特色词汇, 其它任何情况下都严禁使用拼音.
5. 在不影响语义的情况下, id 和 class 名称中可以适当采用英文单词缩写, 比如 col, nav, hd, bd, ft 等, 但切忌自造缩写.
6. id 和 class 名称中的第一个词必须是单词全拼或语义非常清晰的单词缩写, 比如 present, col.
7. 仅在 JavaScript 代码中当作 hook 用的 id 或 class, 命名规则为 J_UpperCamelCase``(请注意, ``J_ 后的首字母也大写！), 其中字母 J 代表 JavaScript, 也是钩子(hook)的象形. 注意：如果在 JavaScript 和 CSS 中都需要用到, 则不用遵守本约定.
8. 在自动化测试脚本中当作 hook 用的 class, 命名规则为 T_UpperCamelCase, 其中字母 T 代表 Test.


## HTML编码规范

### 基本规范

#### 语义

使用符合语义的标签书写 HTML 文档, 选择恰当的元素表达所需的含义

```
<!-- 不推荐 -->
<div onclick="goToRecommendations();">All recommendations</div>

<!-- 推荐 -->
<a href="recommendations/">All recommendations</a>
```


#### 大小写

元素的标签和属性名必须小写, 属性值必须加双引号; 例如

```
<!-- 不推荐 -->
<A HREF='/'>Home</A>

<!-- 推荐 -->
<a href="/">Home</a>
```


#### 缩进

- 使用四个空格来表示缩进，不要使用 tab 键;
- 在块状元素，列表，表格元素后面使用新行，并且对它的子元素进行缩进.
例如

```
<ul>
    <li>
        1
    </li>
</ul>
```

#### 空格

去除比不必要的空格; 例如

```
<!-- 不推荐 -->
<p>test                  </p>

<!-- 推荐 -->
<p>test</p>
```

#### 嵌套

- 元素嵌套遵循 (X)HTML Strict 嵌套规则, 推荐使用Firefox插件 HTML Validator 进行检查;
- 正确区分自闭合元素和非自闭合元素. 非法闭合包括：<br>..</br>、<script />、<iframe />, 非法闭合会导致页面嵌套错误问题;

```
<!-- 不推荐 -->
<title>Test</title>
<article>This is only a test.

<!-- 推荐 -->
<meta charset="utf-8">
<title>Test</title>
<article>This is only a test.</article>
```


#### 引号

使用双引号来标识 html 的属性; 例如

```
<!-- 不推荐 -->
<a class='maia-button maia-button-secondary\>Sign in</a>

<!-- 推荐 -->
<a class="maia-button maia-button-secondary">Sign in</a>
```

#### 自定义属性

通过给元素设置自定义属性来存放与 JavaScript 交互的数据, 属性名格式为 data-xx (例如：data-lazyload-url)

#### DOCTYPE

页面文档类型统一使用HTML5 DOCTYPE. 代码如下：

```
!<DOCTYPE html>
```


#### 编码

声明方法遵循HTML5的规范.推荐使用 utf-8 编码.

```
<meta charset="utf-8">
```

#### 注释

建议对超过10行的页面模块进行注释, 以降低开发人员的嵌套成本和后期的维护成本. 例如：

```
<div id="sample">
    ...
</div> <!-- #sample END -->

<div class="sample">
    ...
</div> <!-- .sample END -->

```

#### 协议

如果链接和当前页面一致则忽略链接的协议部分，例如

```
<!-- 不推荐 -->
<script src="http://www.taobao.com/fp.js">

<!-- 推荐 -->
<script src="//www.taobao.com/fp.js">

/* 不推荐 */
.example {
  background: url(http://www.taobao.com/fp.css);
}

/* 推荐 */
.example {
  background: url(//www.taobao.com/fp.css);
}
```

#### TODO

- 使用 TODO 来标记待做事情，便于后期搜索.
- 在 TODO 后添加 (姓名或邮件) 来表示分类.
例如

```
<!-- TODO(yiminghe): remove duplicate tag -->
<p><span>2</span></p>
```

#### 焦点分离

将表现，行为和结构分离：不要在 html 和模板中加入除了结构以外的东西.
在文档中引入尽可能少的样式和脚本

```
<!-- 不推荐 -->
<!DOCTYPE html>
<title>HTML sucks</title>
<link rel="stylesheet" href="base.css" media="screen">
<link rel="stylesheet" href="grid.css" media="screen">
<link rel="stylesheet" href="print.css" media="print">
<h1 style="font-size: 1em;">HTML sucks</h1>
<p>I’ve read about this on a few sites but now I’m sure:
  <u>HTML is stupid!!1</u>
<center>I can’t believe there’s no way to control the styling of
  my website without doing everything all over again!</center>

<!-- 推荐 -->
<!DOCTYPE html>
<title>My first CSS-only redesign</title>
<link rel="stylesheet" href="default.css">
<h1>My first CSS-only redesign</h1>
<p>I’ve read about this on a few sites but today I’m actually
  doing it: separating concerns and avoiding anything in the HTML of
  my website that is presentational.
<p>It’s awesome!</p>
```

### 元素

#### 结构性元素

- p 表示段落. 只能包含内联元素, 不能包含块级元素;
- div 本身无特殊含义, 可用于布局. 几乎可以包含任何元素;
- br 表示换行符;
- hr 表示水平分割线;
- h1-h6 表示标题. 其中 h1 用于表示当前页面最重要的内容的标题;
- blockquote 表示引用, 可以包含多个段落. 请勿纯粹为了缩进而使用 blockquote, 大部分浏览器默认将 blockquote 渲染为带有左右缩进;
- pre 表示一段格式化好的文本;


#### 头部元素

- title 每个页面必须有且仅有一个 title 元素;
- base 可用场景：首页、频道等大部分链接都为新窗口打开的页面;
- link link 用于引入 css 资源时, 可省去 media(默认为all) 和 type(默认为text/css) 属性;
- style type 默认为 text/css, 可以省去;
- script type 属性可以省去; 不赞成使用lang属性; 不要使用古老的这种hack脚本, 它用于阻止第一代浏览器(Netscape 1和Mosaic)将脚本显示成文字;

    ```
    <!-- 不推荐 -->
    <link rel="stylesheet" href="//www.google.com/css/maia.css"
      type="text/css">

    <!-- 不推荐 -->
    <script src="//www.google.com/js/gweb/analytics/autotrack.js"
      type="text/javascript">

    <!-- 推荐 -->
    <link rel="stylesheet" href="//www.google.com/css/maia.css">

    <!-- 推荐 -->
    <script src="//www.google.com/js/gweb/analytics/autotrack.js">
    ```
- noscript 在用户代理不支持 JavaScript 的情况下提供说明;

####  文本元素

- a a 存在 href 属性时表示链接, 无 href 属性但有 name 属性表示锚点;
- em,strong em 表示句意强调, 加与不加会引起语义变化, 可用于表示不同的心情或语调; strong 表示重要性强调, 可用于局部或全局, strong强调的是重要性, 不会改变句意;
- abbr 表示缩写;
- sub,sup 主要用于数学和化学公式, sup还可用于脚注;
- span 本身无特殊含义;
- ins,del 分别表示从文档中增加(插入)和删除

####  媒体元素

- img 请勿将img元素作为定位布局的工具, 不要用他显示空白图片; 给img元素增加alt属性;例如

    ```
    <!-- 不推荐 -->
    <img src="spreadsheet.png">

    <!-- 推荐 -->
    <img src="spreadsheet.png" alt="Spreadsheet screenshot.">
    ```

- object 可以用来插入Flash;

####  列表元素
- dl 表示关联列表, dd是对dt的解释; dt和dd的对应关系比较随意： 一个dt对应多个dd、多个dt对应一个dd、多个dt对应多个dd, 都合法; 可用于名词/单词解释、日程列表、站点目录;
- ul 表示无序列表;
- ol 表示有序列表, 可用于排行榜等;
- li 表示列表项, 必须是ul/ol的子元素;


#### 表单元素

- 推荐使用 button 代替 input, 但必须声明 type;
- 推荐使用 fieldset, legend 组织表单
- 表单元素的 name 不能设定为 action, enctype, method, novalidate, target, submit 会导致表单提交混乱


#### 文档模板

```
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>Sample page</title>
        <link rel="stylesheet" href="css_example_url" />
    </head>
    <body>
        <div id="page">
            <div id="header">
                页头
            </div>
            <div id="content">
                主体
            </div>
            <div id="footer">
                页尾
            </div>
        </div>
        <script src="js_example_url"></script>
        <script>
        // 你的代码
        </script>
    </body>
</html>
```

## CSS 编码规范

### 编码规范

#### 文件名、文件编码机文件大小
- 文件名必须由小写字母、数字、中划线组成
- 文件必须用UTF-8编码，使用UTF-8（非BOM），在HTML中指定UTF-8编码，在CSS中则不需要特别指定因为默认就是UTF-8
- 单个CSS文件避免过大（建议少于300行）

#### 一般性命名

使用小写字母，复合词以 - 分隔; 例如 nav.css , login-nav.css , login-page

#### id 和类的命名

为 id 和样式类使用有意义或通用的名字，避免由于 css 命名更改引起的不必要的文档或模板改变；例如

```
/* 不推荐： 无意义 */
#yee-1901 {}
 
/* 不推荐： 表现层的命名 */
.button-green {}

/* 推荐: 具体 */
#gallery {}
#login {}
.video {}

/* 推荐: 通用 */
.effect {}
.alt {}

```

id 和 class 的命名长度应该适中，不要太简略也不要太详细；例如

```
/* 不推荐 */
#navigation {}
.atr {}

/* 推荐 */
#nav {}
.author {}
```

#### id和类命名注意事项

- 规则命名中，一律采用小写加中划线的方式，不允许使用大写字母或 _
- 命名避免使用中文拼音，应该采用更简明有语义的英文单词进行组合
- 命名注意缩写，但是不能盲目缩写
- 不允许通过1、2、3等序号进行命名
- 避免class与id重名
- id用于标识模块或页面的某一个父容器区域，名称必须唯一，不要随意新建id
- class用于标识某一个类型的对象，命名必须言简意赅。
- 尽可能提高代码模块的复用，样式尽量用组合的方式
- 规则名称中不应该包含颜色（red/blue）、定位（left/right）等与具体显示效果相关的信息。应该用意义命名，而不是样式显示结果命名。

#### 元素选择器

为了 性能原因 ， 请避免元素选择器和类选择器以及 id 选择器混用;例如

```
/* 不推荐 */
ul#example {}
div.error {}

/* 推荐 */
#example {}
.error {}
```

#### 简写属性名字

为了提高可读性，尽可能的使用简写属性。例如

```
/* 不推荐 */
border-top-style: none;
font-family: palatino, georgia, serif;
font-size: 100%;
line-height: 1.6;
padding-bottom: 2em;
padding-left: 1em;
padding-right: 1em;
padding-top: 0;

/* 推荐 */
border-top: 0;
font: 100%/1.6 palatino, georgia, serif;
padding: 0 1em 2em;
```

#### 常用id的命名

1. 页面结构
 - 容器: container
 - 页头：header
 - 内容：content/container
 - 页面主体：main
 - 页尾：footer
 - 导航：nav
 - 侧栏：sidebar
 - 栏目：column
 - 页面外围控制整体布局宽度：wrapper
 - 左右中：left right center
2. 导航
 - 导航：nav
 - 主导航：mainbav
 - 子导航：subnav
 - 顶导航：topnav
 - 边导航：sidebar
 - 左导航：leftsidebar
 - 右导航：rightsidebar
 - 菜单：menu
 - 子菜单：submenu
 - 标题: title
 - 摘要: summary
3. 功能
 - 标志：logo
 - 广告：banner
 - 登陆：login
 - 登录条：loginbar
 - 注册：regsiter
 - 搜索：search
 - 功能区：shop
 - 标题：title
 - 加入：joinus
 - 状态：status
 - 按钮：btn
 - 滚动：scroll
 - 标签页：tab
 - 文章列表：list
 - 提示信息：msg
 - 当前的: current
 - 小技巧：tips
 - 图标: icon
 - 注释：note
 - 指南：guide
 - 服务：service
 - 热点：hot
 - 新闻：news
 - 下载：download
 - 投票：vote
 - 合作伙伴：partner
 - 友情链接：link
 - 版权：copyright


#### 常用class的命名

1. 颜色:使用颜色的名称或者16进制代码，如

 ```
 .red { color: red; }
 .f60 { color: #f60; }
 .ff8600 { color: #ff8600; }
 ```

2. 字体大小,直接使用”font+字体大小”作为名称，如

 ```
 .font12px { font-size: 12px; }
 .font9pt {font-size: 9pt; }
 ```

3. 对齐样式,使用对齐目标的英文名称，如

 ```
 .left { float:left; }
 .bottom { float:right; }
 ```

4. 标题栏样式,使用”类别+功能”的方式命名，如

 ```
 .barnews { }
 .barproduct { }
 ```

####  0 和单位

对属性值为 0 的情况省略单位；例如

```
margin: 0;
padding: 0;
```

#### 0 前缀情况

省略属性值中的 0 前缀;例如

```
font-size: .8em;
```

16 进制的颜色值表示

尽可能使用 3 个字符的 16 进制颜色值；例如

```
/* 不推荐 */
color: #eebbcc;

/* 推荐 */
color: #ebc;
```

#### 前缀
为了防止冲突，对于应用特定的样式附加应用前缀；例如

```
.login-help {} /* login page */
#detail-note {} /* detail page */
```
hacks

避免 css hack ， 考虑使用特定浏览器前缀表示；例如

```
.lzx-ie6 p {
    margin: 1em 0;
}
```

#### 代码性能优化

- 合并margin、padding、border的-left/-top/-right/-bottom的设置，尽量使用短名称。
- 选择器应该在满足功能的基础上尽量简短，减少选择器嵌套，查询消耗。但是一定要避免覆盖全局样式设置。
- 注意选择器的性能，不要使用低性能的选择器。
- 禁止在css中使用*选择符。
- 除非必须，否则，一般有class或id的，不需要再写上元素对应的tag。
- 0后面不需要单位，比如0px可以省略成0，0.8px可以省略成.8px。
- 如果是16进制表示颜色，则颜色取值应该大写。
- 如果可以，颜色尽量用三位字符表示，例如#AABBCC写成#ABC 。
- 如果没有边框时，不要写成border:0，应该写成border:none 。
- 尽量避免使用AlphaImageLoader 。
- 在保持代码解耦的前提下，尽量合并重复的样式。
- background、font等可以缩写的属性，尽量使用缩写形式 。

### 格式规范

#### 属性声明顺序

- 显示属性：display/list-style/position/float/clear …
- 自身属性（盒模型）：width/height/margin/padding/border
- 背景：background
- 行高：line-height
- 文本属性：color/font/text-decoration/text-align/text-indent/vertical-align/white-space/content…
- 其他：cursor/z-index/zoom/overflow
- CSS3属性：transform/transition/animation/box-shadow/border-radius
- 如果使用CSS3的属性，如果有必要加入浏览器前缀，则按照 -webkit- / -moz- / -ms- / -o- / std的顺序进行添加，标准属性写在最后。
- 链接的样式请严格按照如下顺序添加： a:link -> a:visited -> a:hover -> a:active

```
/* 1 显示属性 */
display: none;
/* 2 自身属性（盒模型）  */
width: 200px;
border: 1px solid;
/* 3 背景  */
background: red;
/* 4 行高  */
line-height: 20px;
/* 5 文本属性  */
color: white;
text-align: center;
text-indent: 2em;
/* 6 其他  */
cursor: pointer;
/* 7 CSS3属性  */
border-radius: 4px;
/* 8 特殊浏览器  */
-webkit-border-radius: 4px;
-moz-border-radius: 4px;
```

#### 块缩进
块的内容应该被缩进；例如

```
@media screen, projection {

  html {
    background: #fff;
    color: #444;
  }

}
```

#### 分号

使用分号结束单个属性的定义；例如

```
/* 不推荐 */
.test {
  display: block;
  height: 100px
}

/* 推荐 */
.test {
  display: block;
  height: 100px;
}
```

#### 空格

在属性名冒号后加一个空格，例如

```
/* 不推荐 */
.test {
  display:block;
}

/* 推荐 */
.test {
  display: block;
}
```

#### 空行

多个选择以及声明间以行分隔；例如

```
/* 不推荐 */
a:focus, a:active {
  position: relative; top: 1px;
}

/* 推荐 */
h1,
h2,
h3 {
  font-weight: normal;
  line-height: 1.2;
}

```

多个 css 规则间以空行分隔；例如

```
html {
  background: #fff;
}

body {
  margin: auto;
  width: 50%;
}
```

#### 引号

尽可能的不用引号，迫不得已时使用单引号.

```
/* 不推荐 */
@import url("//www.google.com/css/maia.css");

html {
  font-family: "open sans", arial, sans-serif;
}

/* 推荐 */
@import url(//www.google.com/css/maia.css);

html {
  font-family: 'open sans', arial, sans-serif;
}
```

#### 注释

成组的 css 规则间用块状注释和空行分离;例如

```
/* Header */

#login-header {}

#login-header-below {}

/* Footer */

#login-footer {}

#login-footer-below {}

/* Gallery */

.login-gallery {}

.login-gallery-other {}
```


#网站规范

## 网站设计规范

### 登录

网站不需要注册，因此没有注册功能，一般登录都放在右上角

注意！
- 不要在后边添加“联系我们”、“收藏”等功能，登录后一行字很长，没有重点
- 尽量不要在主要版面中设计登录窗口，得考虑登录后的状态

### 搜索：各个页面必须有搜索功能

### 面包屑导航

每个页面必须都能返回到上一级和首页。

不同的页面，面包屑不同：
1. 二级页面导航：首页 > 一级导航
2. 三级页面导航：首页>一级导航>二级导航
3. 内容页：首页>一级导航>二级导航>正文

### 页面图片比例规范

整个网站的图片比例一致，定为3:2或者4:3，学校图片的比例一般固定，其他比例会使图片压缩。

### 列表页和内容页分页功能。内容页右下角添加“返回列表”链接。

### 首页新闻标题文字长度规范

标题长度一般不少于15字，而且需考虑添加时间后的空间大小

### 网站宽度

遵循网站主体，宽度960px、980px；涉及到有背景图案的专题页面时，宽度可设置为1440px，正文宽度为980px

### 主要显示的内容保持在第一屏显示完全，需遵循的首屏线，分别是580PX和710PX

在window XP常见分辨率1024×768下我们除掉任务栏，浏览器菜单栏以及状态栏后剩下的网页首屏高度平均值是584，Win7下是574。
在window XP常见分辨率1440×900下我们除掉任务栏，浏览器菜单栏以及状态栏后剩下的网页首屏高度平均值是716。Win7下是706。

### 将网页去色，检查页面的内容、标题等是否还看得清

### 注意抠图有毛边的问题，坚决抵制

### 对齐：注意栏目与栏目的间隔、高度、留白的统一

### 设计的一致性：主要是素材的选用时保持风格一致，都是一个格调

### 网站导航和栏目名称以宋体为主，方便修改

### 需突出的内容部分、新闻标题、栏目标题等样式要明显

### 注意直角容器、圆角容器的锯齿现象

### 图层分组命名规范

建立良好的命名习惯，有利于源文件的移交、重用、提高工作效率与合作。

样例：

- 页头：header
- 页尾：footer
- 栏目：column
- 水平/垂直：H/V
- 摘要：summary
- 鼠标悬停：hover
- 广告横幅：AD/banner
- 内容：content
- 导航： nav
- 整体布局： wrapper
- 标签：tab
- 按钮：btn/button
- 点击：click
- 页面主体：main
- 侧栏：sidebar
- 菜单：submenu
- 滚动：scroll
- 已浏览：visited



### 图片输出
- 使用web格式输出图片
- 色彩少的图片使用gif格式，色彩渐变丰富的图片使用jpg格式，品质为100

## 网站交互规范

### 使用快捷键：回车键

搜索某条新闻、登录时，可以使用回车键直接跳转

### 新窗口链接规范

1. 网站内部页面跳转时，无需重新打开一个窗口
2. 网站内点击外部链接时，重新打开一个窗口，比如友情链接。（学校特殊情况特殊处理）

### 提示信息

提示信息使用弹出层（勿用alert），背景虚化，提示信息要写明错误的原因，比如登录时密码错误还是用户名错误、留言板提交成功等。

### 新闻标题长度规范

新闻标题调用一般根据模板空间大小而定。

- 首页：一般空间较小，一般调用“简短标题”，没有填写“简短标题”时，调用“标题”，显示“标题”的部分文字，鼠标移动到“标题”时，出现“标题”的全部名称。“标题”和“简短标题”可以设置颜色。
- 新闻文字列表页：空间一般较大，调用“标题”。
- 新闻图文列表页，新闻图片列表页：与首页调用相同。
- 内容页：调用“标题”。

### 点击网站logo，返回首页。

### 上传视频

批量上传附件功能；批量上传视频功能，上传任意格式的视频，视频将会默认转换成flv格式，前台显示视频窗口默认大一些，最好与内容的宽度差不多，可以直接播放观看。

### 后台编辑文字在前台显示问题，大小、格式一致

### 栏目下新闻调用问题

如果某个栏目下所有子栏目的新闻会被首页调用，那么在此栏目下新增的子栏目下的新闻也可以被首页调用。

### 子页面有几个子栏目时，进入页面，默认显示第一个子栏目的内容

避免每个子页面模板不一致问题

### 登录问题：一次登录后，退出浏览器将不会保存账号密码

### 新闻详细页图片问题

1. 从图片集中上传的图片，默认文字在上，图片在下。如果内容页的图片为轮换图，那么默认图片在上，文字在下。
2. 不是轮换图时，图片的大小一定要控制好，图片大小一定要与整个页面协调，不能太小。
3. 从图片集中上传的图片，可以对每个图片进行描述。
4. 上传的图片生成缩略图，缩略图的大小分别为：200*200、400*400、600*600、800*800，根据页面不同位置图片大小的不同，选择合适的缩略图。
5. 在内容页，点击缩略图，重新打开一个窗口，显示此缩略图的原图。

### 浏览器优化问题
