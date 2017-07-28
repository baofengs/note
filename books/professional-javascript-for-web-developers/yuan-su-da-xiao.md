### 元素大小

**偏移量：**包括元素在屏幕上占用的所有可监空间。元素可见大小包括：元素高度，宽度，所有的内边距，滚动条大小，边框大小。

| 属性 | 含义 | 具体包括 |
| :--- | :--- | :--- |
| offsetHeight | 元素在垂直方向上占用的空间大小（px） | 元素的高度+水平滚动条的高度+上下边框的高度 |
| offsetWidth | 元素在水平方向上占用的空间大小 | 元素的宽度+垂直滚动条的宽度+左右边框的宽度 |
| offsetTop | 元素左外边框到包含元素的左内边框的距离 |  |
| offsetTop | 元素上外边框到包含元素的上内边框的距离 |  |

![](/assets/WX20170727-160120@2x.png)获取元素在页面上的左 & 上偏移量

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

**客户区大小：**元素内容以及其内边距所占空间的大小

| 属性 | 含义 |
| :--- | :--- |
| clientWidth | 元素的宽度+左右内边距的宽度 |
| clientHeight | 元素的高度+上下内边距的高度 |

![](/assets/WX20170727-200012@2x.png)获取浏览器视口大小

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

**滚动大小：**包含滚动内容的元素的大小。

| 属性 | 含义 | 用途 |
| :--- | :--- | :--- |
| scrollHeight | 没有滚动条情况下，元素内容的总高度 | 确定元素内容的大小 |
| scrollWidth | 没有滚动条情况下，元素内容总宽度 | 确定元素内容的大小 |
| scrollLeft | 被隐藏在内容区左侧的像素数 | 改变元素滚动位置 |
| scrollTop | 被隐藏在内容上方的像素数 | 改变元素滚动位 |

![](/assets/WX20170727-204826@2x.png)兼容问题

| 浏览器 | clientWidth/clientHeight与 scrollWidth/scrollHeight 关系 |
| :--- | :--- |
| FireFox | 两组数相同；代表文档内容区域实际尺寸 |
| Opeta/Safari ^3.1/Chrome | scroll\*表示视口大小，client\*表示文档内容区域大小 |
| IE（标准模式） | scroll\*表示文档区域大小；client\*表示视口大小 |

跨浏览器模式下获取文档高度精确结果

```js
const docHeight = Math.max(document.documentElement.scrollHeight,
                           document.documentElement.clientHeight);
const docWidth = Math.max(document.documentElement.scrollwidth,
                           document.documentElement.clientWidth);
```

跨浏览器获取元素大小方法：

```js
function getBoundingClientRect(element) {
    var scrollTop = document.documentElement.scrollTop;
    var scrollLeft = document.documentElement.scrollLeft;
    if (element.getBoundingClientRect) {
        GetBoundingClientRectExample.htm
        if (typeof arguments.callee.offset != "number") {
            var temp = document.createElement("div");
            temp.style.cssText = "position:absolute;left:0;top:0;";
            document.body.appendChild(temp);
            arguments.callee.offset = -temp.getBoundingClientRect().top - scrollTop;
            document.body.removeChild(temp);
            temp = null;
        }
        var rect = element.getBoundingClientRect();
        var offset = arguments.callee.offset;
        return {
            left: rect.left + offset,
            right: rect.right + offset,
            top: rect.top + offset,
            bottom: rect.bottom + offset
        };
    } else {
        var actualLeft = getElementLeft(element);
        var actualTop = getElementTop(element);
        return {
            left: actualLeft - scrollLeft,
            right: actualLeft + element.offsetWidth - scrollLeft,
            top: actualTop - scrollTop,
            bottom: actualTop + element.offsetHeight - scrollTop
        }
    }
}
```



