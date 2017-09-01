## CSS 布局

### display 属性

| 属性值 | 含义 | 举例 |
| :--- | :--- | :--- |
| block | 块级元素盒：尽可能撑满整个容器 | p、form、header、footer、section |
| inline | 行内元素盒：可以在段落中包裹文字，不打乱布局 | span、a |
| none | 不删除元素情况下隐藏元素的显示 | display: none;元素不占据原有空间；visibility: hidden;元素仍占据空间 |
| list-item | 生成一个容纳内容和单独的列表行内元素盒的块状盒 |  |

> 其他详情详细介绍查看：[https://developer.mozilla.org/zh-CN/docs/Web/CSS/display](https://developer.mozilla.org/zh-CN/docs/Web/CSS/display)

#### margin: auto;

```
#element {
    width: 600px;
    margin: 0 auto;
}
```

1. width: 防止块级元素撑满整个容器
2. 设置 margin: 0 auto; 保证该元素相对于父元素水平居中，元素占据指定宽度，剩余宽度一分为二，其中父元素必须有宽度设置。
3. 不足：当浏览器窗口宽度比元素宽度小时，会产生水平滚动条

#### max-width

```
#element {
    max-width: 960px;
    margin: 0 auto;
}
```

* 通过使用 max-width，可以让浏览器更好的处理小窗口情况

#### 盒模型

当设置了元素的宽度，由于元素中的内边距 & 内边框，导致元素实际的展示效果比预设的值要大

```
.simple {
    width: 500px;
    margin: 20px auto;
}

.fancy {
    width: 500px;
    margin: 20px auto;
    padding: 20px;
    border-width: 20px;
}
```

* .fancy 元素的实际宽度 = width + padding.width \* 2 + border.width \* 2;
* .simple 元素的实际宽度 = width

#### box-sizing: border-box;

当一个元素设置了该属性，则此元素的内边距 & 内边框不再会增加他的宽度

```
* {
    -webkit-box-sizing: border-box;
       -moz-box-sizing: border-box;
            box-sizing: border-box;
}
```

#### position

| 属性值 | 含义 |
| :--- | :--- |
| static （默认值） | 任意的 position: static 元素不会被特殊的定位 |
| relative | 表现和 static 一样；如果元素设置了left、right、top、bottom 属性之后，则会相对于自身位置进行偏移，不影响其他元素位置。（不脱离文档流） |
| fixed | 相对视窗来定位 （脱离文档流）通过 top、right、bottom、left 设置元素位置 |
| absolute | 相对于最近"positioned" 祖先元素定位，如果没有找到，则相对于 body 元素定位 （脱离文档流） |

```
.relative {
    position: relative;
    width: 600px;
    height: 600px;
}
.item {
    position: absolute;
    width: 60px;
    height: 60px;
    top: -10px;
    right: 0;
}
```

> [https://jsbin.com/wuneroziva/edit?html,css,output](https://jsbin.com/wuneroziva/edit?html,css,output)

#### float

指定元素沿着容器左侧或者右侧防止，同时允许文字或者内联元素环绕它





