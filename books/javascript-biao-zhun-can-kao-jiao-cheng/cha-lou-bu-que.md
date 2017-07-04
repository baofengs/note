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

### 数据类型

* 原始类型
  * 数值：整数 & 小数
  * 字符串：字符组成的文本
  * 布尔值：true & false，以下根据转换规则转换后为 false，其他都为 true
    * undefined
    * null
    * false
    * NaN
    * 0
    * '' OR ""
* 特殊值
  * undefined：未定义 OR 不存在
  * null：无值
* 合成类型

  * 对象：各种值组成的集合

    * 狭义对象：object

    * 数组：array

    * 函数：function

### parseInt & parseFloat

parseInt\(\)：1）字符串转化为整数；2）进制转化

parseFloat\(\)：字符串转化为浮点数





