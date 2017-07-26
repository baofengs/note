### 图片懒加载

#### 原理

* 图片位置放置一个占位符，真实的图片的地址放在 data-src 属性中
* 监听 window.onscroll 在每一次滚动时，将图片到窗体顶部的距离与滚动距离 + 窗体可视距离比较，如果后者大，则将位于可视区域中的图片的真实图片地址赋值给 img 的 src 属性

示例：[https://sbaof.github.io/code-pieces/fe/public/lazyLoad/](https://sbaof.github.io/code-pieces/fe/public/lazyLoad/)

