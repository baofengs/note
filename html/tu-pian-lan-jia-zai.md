### 图片懒加载

#### 原理

* 图片位置放置一个占位符，真实的图片的地址放在 data-src 属性中
* 监听 window.onscroll 在每一次滚动时，将图片到窗体顶部的距离与滚动距离 + 窗体可视距离比较，如果后者大，则将位于可视区域中的图片的真实图片地址赋值给 img 的 src 属性

```js
var winHeight = screen.availHeight;
function loadImage() {
    // 滚动距离
    var nowHeight = document.body.scrollTop || document.documentElement.scrollTop;
    console.log('nowHeight: ', nowHeight, ' winHeight: ', winHeight);
    if (images.length > 0) {
        images.map((image, index) => {
            if (nowHeight + winHeight > image.offsetTop) {
                image.src = image.dataset.src;
                images.splice(index, 1);
            }
        })
    } else {
        window.removeEventListener('scroll', loadImage);
    }
}
window.addEventListener('scroll', loadImage);
```

示例：[https://sbaof.github.io/code-pieces/fe/public/lazyLoad/](https://sbaof.github.io/code-pieces/fe/public/lazyLoad/)

参考：[http://jzleung.github.io/2016/08/05/without-jquery-lazyload-js/](http://jzleung.github.io/2016/08/05/without-jquery-lazyload-js/)

