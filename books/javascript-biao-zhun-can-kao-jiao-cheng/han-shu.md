### 函数声明

* function 命令

```js
function init () {
    console.log('foo');
}
```

* 函数表达式

```js
// 讲一个匿名函数赋值给一个变量
var foo = function () {
    console.log('bar');
};

// 带有函数名的函数赋值给一个变量，则函数名只在函数内部有效
var foo = function bar () {
    console.log(typeof bar); // function
}

bar  // Uncaught ReferenceError: bar1 is not defined
*好处*：1）函数体内部调用自身；2）方便排错，据说是除错工具显示函数调用栈是将显示函数名，而不提示这里是一个匿名函数
```

* Function 构造函数

```js
// 构造函数最后一个参数会被当成函数体，其他的都是这个函数体的参数
var add = new Function(
    'x',
    'y',
    'return x + y';
)
 <==>
 function add (x, y) {
     return x + y;
 }
```

### 函数重复声明

同一个函数可以多次声明，后边的声明覆盖前面的

### 函数是第一等公民

Js 中将函数看做是一种值，与数值，字符串等地位相同，故称为函数为第一等公民



