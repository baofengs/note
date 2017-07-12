### 使用::selection：自定义文本选中状态

适用css属性：color, background-color, cursor, outline, text-decoration, text-emphasis-color、text-shadow

示例：

```CSS
// HTML
<div class="foo">this is foo</div>
<div class="bar">this is bar</div>

// CSS
// 设置全局
::selection {
  color: red;
  background-color: #ccc;
  text-decoration: underline;
}

// 设置单个元素 selection 样式
.foo::selection {
  color: blue;
}

.bar::selection {
  background-color: blue;
}
```

MDN：[https://developer.mozilla.org/zh-CN/docs/Web/CSS/::selection](https://developer.mozilla.org/zh-CN/docs/Web/CSS/::selection)

codePen：[https://codepen.io/SanBf/pen/PjXRYL](https://codepen.io/SanBf/pen/PjXRYL)





