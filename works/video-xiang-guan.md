# 开发中使用 &lt;video&gt; 遇到的问题 & 解决

* 编码格式问题

  * 浏览器对 H.264 视频编码格式兼容性比较好，建议使用

* 同为 H.264 编码格式，win7 下 ie 内核浏览器无法播放

  * 微信是个神奇而又好用的东西，通过微信传输，实际上就是让微信帮忙转一下码就 OK 了

* 对于垂直放置的视频，只设置高度，宽度自适应，加载视频时会有黑色 OR 白色（设置 background 之后的表现，不同系统 OR 浏览器表现不一致）的背景

  * 原因可能是默认情况就是会显示横放的矩形背景
  * 建议设置默认宽度，高度自适应方式，可参考石墨首页视频部分（[https://shimo.im/）](https://shimo.im/）)

* 多格式类型（.mp4, .ogg...）视频设置方式

```HTML
<video width="1040" autoplay="" loop="" poster="">
    <source src="https://assets-cdn.shimo.im/assets/images/home/index/video/op_final-7c98f06236.mp4" type="video/mp4">
    <source src="https://assets-cdn.shimo.im/assets/images/home/index/video/op_final-b0cd06a163.ogg" type="video/ogg">
</video>

// 其他方式设置 <video>
<video width="1040" src="https://xxx.com/video/foo.mp4" autoplay="" loop="" poster="">
</video>
```

* &lt;video&gt; 中使用多个 &lt;source&gt; 时，可使用相同视频格式类型，浏览器会加载首个可以播放的视频
* 浏览器 HTML5 测试
  * [http://chrome.360.cn/test/html5/index.html](http://chrome.360.cn/test/html5/index.html)
* 其他问题
  * 为什么video不能填满整个父级div？底部有黑边？
    * [https://segmentfault.com/q/1010000008653026\#answers-title](https://segmentfault.com/q/1010000008653026#answers-title)
* * HTML5中Video开发遇到的一些坑： [https://zhuanlan.zhihu.com/p/22675552](https://zhuanlan.zhihu.com/p/22675552)
* 新版本 Safari 11.0 默认设置会禁用带有声音视频的自动播放
  * 解决方案：
    * 删除视频的音轨
    * 添加 muted 属性（详情见此https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video）
  * 官方给出的是使用静音标签页和窗口 [https://support.apple.com/zh-cn/guide/safari/ibrw29c6ecf8/mac](https://support.apple.com/zh-cn/guide/safari/ibrw29c6ecf8/mac)
  * ![](/assets/WechatIMG465.jpeg)



