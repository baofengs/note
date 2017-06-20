## 输入框内文本

```HTML
<div>
    <pre>`${data}`</pre>
</div>
```

```CSS
pre {
    word-break: break-all;
    // 设置元素中空白符显示模式为：pre-wrap，即连续的空白符会被合并，换行(\n) OR <br> OR 填充 line 盒子时才会换行
    white-space: pre-wrap;
}
```



