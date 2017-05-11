# CSS

> 概念
>
> 浏览器渲染过程
>
> 引入方式：1. 外部样式 2 内部样式 3. 内联样式
>
> 选择器：

层叠样式表，用于指定如何向用户展示文档的语言---指定它们的风格，布局等。

多设备支持：`显示器、 投影仪、  打印机`

## 浏览器渲染过程

![](/assets/WX20170508-133437.png)

## 引入方式

* 外部方式

```
<link rel="stylesheet" href="style.css">
```

* 内部样式

```
<style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
</style>
```

* 内联样式·

```
 <p style="color:red;">This is my first CSS example</p>
```

## 选择器

* 元素选择器（类型选择器）

```css
html {
    background: #BADA55;
}
h1 {
    color: silver;
}
```

* 选择器分组

```css
/* 都好分割 */
p, h2 {
    color: #ccc;    
}
```

* 类选择器

```css
*.importent {
   pointer: curse;   
}
.importent {
   font-size: 16px;
}
/* 包含 importent 的所有`p`元素 */
p.importent {
   display: inline-block;
}
/* 同时包含`importent` & `warning` */
.importent.warning {
   background: silver;
}
```

* id 选择器

```css
*#intro {
    font-weight: 600;
}
#intro {
    font-weight: blod;
}
```

* 属性选择器

```css
/* 包含`title`的所有元素 */
*[title] {
    color: #BADA55;
}
/* 对有`href`属性的`a`元素 */
a[href] {
    color: #BADA55;
}
/*具体属性值*/
a[href="http://www.baidu.com"] {...}

/* 根据部分属性值: `class`中包含`importent`的元素 */
p[class~="importent"] {...}
img[title~="foo"] {...}

/* 子串匹配 */
/* 以`bar`开头 */
p[foo^="bar"] {...}
/* 以`bar`结尾 */
p[foo$="bar"] {...}
/* 包含子串`bar` */
p[foo*="bar"] {...}

/* 特定属性选择类型 */ 
/* 以`en`开头，该值必须是整个单词 */
p[lang |= "en"] {...}
```

* 后代选择器

```css
h1 em {
    position: relative;
}
```

* 子元素选择器

```css
h3 > strong {
    color: #BADA55;
}
/* 选择作为`td`子元素的`p`元素，这个`td`本身从`table`继承，同时该`table`包含一个`company`属性*/
table.company td > p {
    border: 1px solid silver;
}
```

* 相邻兄弟选择器

```css
/* 选择紧在`h1`后的`p`元素，两者拥有相同的父元素 */
h1 + p {
    display: inline-block;
}
/* 选择紧邻`table`后的所有`ul`兄弟元素，`table`本身包含于`body`中，`body`元素本身属于`html`的子元素 */
html > body table + ul {
    margin-top: 10px;
}
```

* 伪类

```css
/* 锚伪类 */
a:link { ... }
a:visited { color: red; }
a:hover { color: blue; }
a:active { color: green; }
/* **注意**：`hover`必须置于·link· & ·visited·之后；·active·必须置于·hover·之后 */

/* 父元素的第一个子元素 */

p:first-child {
    font-weight: bold;
}

/* lang：w3c */
<html>
<head>

<style type="text/css">
q:lang(no)
   {
   quotes: "~" "~"
   }
</style>

</head>

<body>
<p>文字<q lang="no">段落中的引用的文字</q>文字</p>
</body></html>
```

* 伪元素

```css
/* first-line: 只能用于块级元素 */
/* p元素的第一行 */
p:first-line {
    color: #BADA55;
}

/* first-letter 同上*/
p:first-letter {
    color: green;
}

/* before */
div:before {
    content: 'Foo';
}

/* after */
div:after {
    content: 'Bar';
}
```



