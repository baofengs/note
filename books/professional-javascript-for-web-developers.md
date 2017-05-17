### 高级定时器:setTimeout & setInterval

* Javascript运行于单线程环境中

* 定时器是计划代码在未来某个时间执行

* 浏览器只负责排序，指派某段代码在某个时间运行的优先级

* 定时器队列工作方式：当特定的时间过去后将代码插入队列，等到 Javascript 进程空闲时，尽快执行。注意，给队列插入代码并不表示立即执行，只能表示尽快执行

#### 重复的定时器

* setInterval\(\)：创建的定时器保证定时器代码规则的插入到队列中，存在的问题：

  * 某些间隔会被跳过
  * 多个定时器的代码执行之间的间隔可能会比预期小

  ![](/assets/WX20170517-112927.png)

* 为避免 setInterval 的两个问题，使用链式 setTimeout\(\)调用

```js
setTimeout(function() {
    // handling...

    // arguments.callee：获取当前执行函数的引用 & 为其设置一个新的定时器
    setTimeout(arguments.callee, interval);
}, interval);

/*
 * 使用 arguments.callee 好处：在之前一个定时器执行完成之前，不会向队列中插入新的定时器
 * 确保了不会缺失任何时间间隔
 */
```

* 实例：将一个&lt;div&gt;元素向右移动，在200px 处停止

```js
setTimeout(function() {
    const div = document.getEelementById("myDiv");
    let left = parseInt(div.style.left) + 5;
    if (left < 200) {
        setTimeout(arguments.callee, 50);
    }
}, 50);
```



