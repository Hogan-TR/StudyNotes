## 简介

CSS - **层叠样式表**（Cascading Style Sheets）



## 语法

构成：选择器 + 一条或多条声明（声明以`';'`结束）

注释：`/*...*/`



## id 和 class 选择器

### id 选择器

```css
/* 用'#'来定义 */
#para1 {
    text-align: center;
    color: red;
}
```

### class 选择器

```css
/* 用'.'显示 */
.center {
    text-align: center;
}
/* 所有p元素使用 class="center" 的文本居中*/
p.center {
    text-align: center;
}
```



## 创建

### 外部样式表

应用于多个页面

> 属性值和单位之间不能有空格

```html
<head>
<link rel="stylesheet" type="text/css" href="style.css">
</head>
```

### 内部样式表

单个文档有特殊样式

```html
<head>
<style>
hr {color: siema;}
p {margin-left: 20px;}
body {backgroud-image: url("images/back40.gif");}
</style>
</head>
```

### 内联样式

```html
<p style="color: siema; margin-left: 20px">Just test</p>
```

### 多重样式及优先级

如果某些属性在不同的样式表中被同样的选择器定义，则属性值将从更具体地样式表中被继承。

优先级：**内联样式 > 内部样式 > 外部样式 > 浏览器默认样式**

```html
<head>
    <!-- 外部样式 style.css -->
    <link rel="stylesheet" type="text/css" href="style.css"/>
    <!-- 设置：h3{color:blue;} -->
    <style type="text/css">
      /* 内部样式 */
      h3{color:green;}
    </style>
</head>
<body>
    <h3>测试！</h3>
</body>
```

> 注意：若外部样式放在内部样式的后面，则外部样式将覆盖内部样式。



## 背景

### background-color

颜色定义方式

- 十六进制
- RGB
- 颜色名称

```css
/* 页面的背景色 */
body {
    background-color: #b0c4de;
}
```

### background-image

默认情况下，背景图像进行**平铺(水平/垂直)重复**显示，以覆盖整个元素实体

```css
body {
    background-image: url('page.gif');
}
```

### background-repeat

```css
/* 图像仅水平方向平铺 repeat-x */
/* 不平铺 -> no-repeat */
body {
    backgroud-image: url('gradient.png');
    backgroud-repeat: repeat-x;
}
```

### background-position

改变图像在背景中的位置

```css
body {
    backgroud-image: url('tree.png');
    background-repeat: no-repeat;
    background-position: right top;
}
```

### 简写属性

属性值的顺序：

- background-color
- background-image
- background-repeat
- background-attachment
- background-position

```css
body {background:#ffffff url('tree.png') no-repeat right top;}
```



## 文本格式

### 颜色 color

> 对于W3C标准的CSS，若定义了颜色属性，则**必须**定义背景色属性

```css
body {color:red;}
h1 {color:#00ff00}
h2 {color:rgb(255,0,0)}
```

### 对齐方式 text-align

文本排列属性是用来设置文本的**水平对齐**方式

- 居中 - `center`
- 左 / 右对齐 - `left / right`
- 两端对齐（"`justify`"，每行被展开维宽度相等，左、右外边距是对齐）

```css
h1 {text-align:center;}
p.date {text-align:right;}
p.main {text-align:justify;}
```

### 修饰 text-decoration

设置或删除文本的装饰（主要用来**删除**链接的下划线）

```css
/* 删除 */
a {text-decoration:none;}

/* 装饰 */
h1 {text-decoration:overline;}
h2 {text-decoration:line-through;}
h3 {text-decoration:underline;}
```

### 转换 text-transform

指定在一个文本中的大写和小写字母

```css
p.uppercase {text-transform:uppercase;}   /* 大写 */
p.lowercase {text-transform:lowercase;}   /* 小写 */
p.capitalize {text-transform:capitalize;} /* 首字母大写 */
```

### 缩进 text-indent

指定文本第一行的缩进

```css
p {text-indent:50px;}
```



## 字体

### 字体系列 font-family

- 通用字体系列 - 拥有相似外观的字体系统组合
- 特定字体系列 - 一个特定的字体系列

> 注意：若字体系列的名称超过一个字，则必须用引号，如 font-family: "宋体"

```css
p {font-family:"Times New Roman", Times, serif;}
```

### 字体样式 font-style

属性的三个值：

- 正常 - 正常显示文本
- 斜体 - 以斜体字现实的文字
- 倾斜的文字 - 文字向一边倾斜

```css
p.normal {font-style:normal;}
p.italic {font-style:italic;}
p.oblique {font-style:oblique;}
```

### 字体大小 font-size

字体大小的值可以是绝对或相对的大小

#### 绝对大小

- 设置一个指定大小的文本
- 不允许用户在所有浏览器中改变文本大小
- 确定了输出的物理尺寸时，绝对大小很有用
- `xx-small x-small small medium large x-large xx-large`

#### 相对大小

- 相对于周围的元素来设置大小
- 允许用户在浏览器中改变文字大小
- `smaller larger`

> 默认大小和普通文本段落一样，16px = 1em

```css
/* 设置文字的大小与像素 */
/* 可以通过缩放来调整文本大小（整个页面）*/
h1 {font-size:40px;}

/* 通过em */
/* px/16=em */
h2 {font-size:0.875em;}

/* 百分比与em结合 */
/* 所有浏览器中，设置<body>元素的默认字体大小的时百分比 */
/* % => 基于父元素的一个百分比值 */
body {font-size:100%;}
h1 {font-size:2.5em;}
h2 {font-size:1.875em;}
p {font-size:0.875em;}
```



## 链接

### 链接状态

- `a:link`：正常，未被访问
- `a:visited`：已访问
- `a:hover`：用户鼠标放在链接上
- `a:active`：链接被点击

```css
a:link {color:#000000;}
a:visited {color:#00FF00;}
a:hover {color:#FF00FF;}
a:active {color:#0000FF;}
```

### 链接样式

#### 文本修饰

```css
a:link {text-decoration:none;}
a:visited {text-decoration:none;}
a:hover {text-decoration:underline;}
a:active {text-decoration:underline;}
```

#### 背景颜色

```css
a:link {background-color:#B2FF99;}
a:visited {background-color:#FFFF85;}
a:hover {background-color:#FF704D;}
a:active {background-color:#FF704D;}
```



## 列表

### 作用

- 设置不同的列表项标记为有序列表
- 设置不同的列表项标记为无序列表
- 设置列表项标记为图像

### 列表项标记 list-style-type

```css
ul.a {list-style-type:circle;}
ul.b {list-style-type:square;}

ol.c {list-style-type:upper-roman;}
ol.d {list-style-type:lower-alpha;}
```

### 列表项标记-图像 list-style-image

```css
ul {
    list-style-image: url('squrple.gif');
}
```

### 简写属性

顺序：`list-style-type, list-style-position, list-style-image`

```css
ul {list-style: square url('squrple.gig');}
```



## 表格

### 边框 border

```css
table, th, td {
    border: 1px solid black;
}
```

### 折叠边框 border-collapse

设置表格的边框是否被折叠成一个单一的边框或隔开

```css
table {border-collapse:collapse;}
```

### 宽度和高度

```css
table {width:100%;}
th {height:50px;}
```

### 文字对齐

```css
/* 水平对齐 */
td {text-align:right;}

/* 垂直对齐 */
td {height:50px; vertical-align:bottom;}
```

### 填充 padding

如果在表的内容中控制空格之间的边框，应使用td和th元素的填充属性

```css
td {padding:15px;}
```

### 颜色

```css
table, td, th {
    border:1px solid green;
}
th {
    background-color:green;
    color:white;
}
```



## 盒子模型 Box Model

- **Margin 外边距** \- 清除边框外的区域，外边距是透明的
- **Border 边框** \- 围绕在内边距和内容外的边框
- **Padding 内边距** \- 清除内容周围的区域，内边距是透明的
- **Content 内容** \- 盒子的内容，显示文本和图像

### 元素的宽度和高度

> 当指定一个CSS元素的宽度和高度属性时，仅是设置**内容**区域的宽度和高度。
>
> **完全大小**的元素，还必须添加填充、边框和边距。

```css
div {
    width: 300px;
    border: 25px solid green;
    padding: 25px;
    margin: 25px;
}
```

总元素的宽度=宽度+左填充+右填充+左边框+右边框+左边距+右边距

总元素的高度=高度+顶部填充+底部填充+上边框+下边框+上边距+下边距



## 边框

### 边框样式 border-style

| 属性 | 值   |
| ---- | ---- |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |

