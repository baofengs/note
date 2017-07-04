### 变量提升

Js引擎工作方式：先解析代码，获取所有被声明的变量，然后一行行地运行。这照成的结果，就是所有的变量声明语句，都会提升到代码的头部。

```js
// 先调用，后声明
console.log(a);
var a = 1;
 undefined
<= undefined

<=>

var a;
console.log(a);
a = 1;

// 调用未声明的变量
console.log(b);
// Uncaught ReferenceError: b is not defined
```



