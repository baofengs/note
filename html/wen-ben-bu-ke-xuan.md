## 使用 CSS 设置网页文本不可选中

```HTML
<div class="no-select">
    You can't select me! HaHa
</div>
```

```CSS
.no-select {
    user-select: none;
}
```

## 引申

```CSS
// 在一个HTMl编辑器中，当双击子元素或者上下文时，那么包含该子元素的最顶层元素也会被选中。
.select-all {
    user-select: all;
}
```

MDN user-select: [https://developer.mozilla.org/zh-CN/docs/Web/CSS/user-select\]](https://developer.mozilla.org/zh-CN/docs/Web/CSS/user-select]%28https://developer.mozilla.org/zh-CN/docs/Web/CSS/user-select\)

Code Pen: [https://codepen.io/SanBf/pen/QgpoKJ](https://codepen.io/SanBf/pen/QgpoKJ)

