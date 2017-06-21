### 函数声明

* function 命令

```Javascript
function init () {
    console.log('foo');
}
```

* 函数表达式

```Javascript
// 讲一个匿名函数赋值给一个变量
var foo = function () {
    console.log('bar');
};

// 带有函数名的函数赋值给一个变量，则函数名只在函数内部有效
var foo = function bar () {
    console.log(typeof bar); // function
}

bar  // Uncaught ReferenceError: bar1 is not defined
```





