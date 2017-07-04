## 自定义滚动条

### IE

* scrollbar-arrow-color: color; /三角箭头的颜色/
* scrollbar-face-color: color; /立体滚动条的颜色（包括箭头部分的背景色）/
* scrollbar-3dlight-color: color; /立体滚动条亮边的颜色/
* scrollbar-highlight-color: color; /滚动条的高亮颜色（左阴影？）/
* scrollbar-shadow-color: color; /立体滚动条阴影的颜色/
* scrollbar-darkshadow-color: color; /立体滚动条外阴影的颜色/
* scrollbar-track-color: color; /立体滚动条背景颜色/
* scrollbar-base-color:color; /滚动条的基色/

### webkit

* 伪元素

  * ::-webkit-scrollbar 滚动条整体部分
  * ::-webkit-scrollbar-button 滚动条两端的按钮
  * ::-webkit-scrollbar-track 外层轨道
  * ::-webkit-scrollbar-track-piece 内层轨道，滚动条中间部分（除去）
  * ::-webkit-scrollbar-thumb （拖动条？滑块？滚动条里面可以拖动的那个，肿么翻译好呢？）
  * ::-webkit-scrollbar-corner 边角
  * ::-webkit-resizer 定义右下角拖动块的样式

* 伪类

  * :horizontal – horizontal伪类应用于水平方向的滚动条
  * :vertical – vertical伪类应用于竖直方向的滚动条
  * :decrement – decrement伪类应用于按钮和内层轨道\(track piece\)。它用来指示按钮或者内层轨道是否会减小视窗的位置\(比如，垂直滚动条的上面，水平滚动条的左边。\)
  * :increment – increment伪类和decrement类似，用来指示按钮或内层轨道是否会增大视窗的位置\(比如，垂直滚动条的下面和水平滚动条的右边。\)
  * :start – start伪类也应用于按钮和滑块。它用来定义对象是否放到滑块的前面。
  * :end – 类似于start伪类，标识对象是否放到滑块的后面。
  * :double-button – 该伪类以用于按钮和内层轨道。用于判断一个按钮是不是放在滚动条同一端的一对按钮中的一个。对于内层轨道来说，它表示内层轨道是否紧靠一对按钮。
  * :single-button – 类似于double-button伪类。对按钮来说，它用于判断一个按钮是否自己独立的在滚动条的一段。对内层轨道来说，它表示内层轨道是否紧靠一个single-button。
  * :no-button – 用于内层轨道，表示内层轨道是否要滚动到滚动条的终端，比如，滚动条两端没有按钮的时候。
  * :corner-present – 用于所有滚动条轨道，指示滚动条圆角是否显示。
  * :window-inactive – 用于所有的滚动条轨道，指示应用滚动条的某个页面容器\(元素\)是否当前被激活。\(在webkit最近的版本中，该伪类也可以用于::selection伪元素。webkit团队有计划扩展它并推动成为一个标准的伪类\)
  * 另外，:enabled、:disabled、:hover 和 :active 等伪类同样可以用于滚动条中。

DEMO：

LINKS：

* 前端观察 [https://www.qianduan.net/css-custom-scroll-bar-style/](https://www.qianduan.net/css-custom-scroll-bar-style/)
* CSS自定义浏览器滚动条样式 [http://alfred-sun.github.io/blog/2014/12/24/scrollbar-customized-with-css-style/](http://alfred-sun.github.io/blog/2014/12/24/scrollbar-customized-with-css-style/)



