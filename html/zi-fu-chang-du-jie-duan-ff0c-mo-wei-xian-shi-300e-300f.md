## 文本长度限制，超出部分显示...

```HTML
<div class="container">
  <div class="item" title="两情若是久长时，又岂在朝朝暮暮">两情若是久长时，又岂在朝朝暮暮</div>
  <span class="item block" title="肉眼凡胎，岂能窥视仙人变化">肉眼凡胎，岂能窥视仙人变化</span>
</div>
```

```CSS
.container {
  width: 8em;
  border: 1px solid #BADA55;
}

.item {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.item:hover {
  cursor: pointer;
}

.block {
  display: block;
}
```

示例展示：https://codepen.io/SanBf/pen/VWbLGv





