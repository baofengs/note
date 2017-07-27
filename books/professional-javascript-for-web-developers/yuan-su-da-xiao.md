### 元素大小

偏移量：包括元素在屏幕上占用的所有可监空间。元素可见大小包括：元素高度，宽度，所有的内边距，滚动条大小，边框大小。

| 属性 | 含义 | 具体包括 |
| :--- | :--- | :--- |
| offsetHeight | 元素在垂直方向上占用的空间大小（px） | 元素的高度+水平滚动条的高度+上下边框的高度 |
| offsetWidth | 元素在水平方向上占用的空间大小 | 元素的宽度+垂直滚动条的宽度+左右边框的宽度 |
| offsetTop | 元素左外边框到包含元素的左内边框的距离 |  |
| offsetTop | 元素上外边框到包含元素的上内边框的距离 |  |



获取元素在页面上的左 & 上偏移量

```js
// 通过元素的 offsetLeft + offsetParent 属性获取
function getElementLeft(element) {
    var actualLeft = element.offsetLeft;
    var current = element.offsetParent;
    
    while(current != null) {
        actualLeft += current.offsetParent;
        current = current.offsetParent;
    }
    return actualLeft;
}

function getElementTop (element) {
    var actualTop = element.offsetTop;
    var current = element.offsetParent;
    
    while(current !== null) {
        actualLeft += current.offsetParent;
        current = current.offsetParent;
    }
}
```

客户区大小：元素内容以及其内边距所占空间的大小

| 属性 | 含义 |
| :--- | :--- |
| clientWidth | 元素的宽度+左右内边距的宽度 |
| clientHeight | 元素的高度+上下内边距的高度 |

获取浏览器视口大小

```js
function getViewport() {
  if (document.compatMode == 'BackCompat') {
    return {
      width: document.body.clientWidth,
      height: document.body.clientHeight
    }
  } else {
    return {
      height: document.documentElement.clientHeight,
      width: document.documentElement.clientWidth
    }
  }
}
```







