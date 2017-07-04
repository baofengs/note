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

## 数值

### parseInt & parseFloat

parseInt\(\)：

* 字符串转化为整数

```
parseInt('123') // 123
parseInt('  123  ') // 123
parseInt(1.23) // 1
// 自动转化为科学计数法
parseInt(1000000000000000000000.5) // 1
// 等同于
parseInt('1e+21') // 1

parseInt(0.0000008) // 8
// 等同于
parseInt('8e-7') // 8
```

* 进制转化：parseInt方法还可以接受第二个参数（2到36之间），表示被解析的值的进制，返回该值对应的十进制数。 如果第二个参数是0、undefined和null，则直接忽略。

```
parseInt('1000', 2) // 8
parseInt('1000', 6) // 216
parseInt('1000', 8) // 512

// 第二个参数取值不合法 或者 0、null、undefined
parseInt('10', 37) // NaNparseInt('10', 37) // NaN
parseInt('10', 1) // NaN
parseInt('10', 0) // 10
parseInt('10', null) // 10
parseInt('10', undefined) // 10

// 第一个参数中含有第二个参数代表进制无意义的数字
parseInt('1546', 2) // 1
parseInt('546', 2) // NaN
```

parseFloat\(\)：字符串转化为浮点数

```
parseFloat('3.14') // 3.14
parseFloat('3.14e+2') // 314
parseFloat('\t\v\r12.34\n ') // 12.34

// 不是字符串 OR 第一个字符不能转化为浮点数
parseFloat([]) // NaN
parseFloat('FF2') // NaN

// 空字符串转化为 NaN
parseFloat('') // NaN
```

### 字符串

#### 反斜杠特殊用法

* \HHH：\后跟三个八进制数，对应 Unicode 码点，表示一个字符，一共256个
* \xHH：\x后跟两个十六进制数，同上
* \uXXXX：\u 后跟四个十六进制数，同上

```
'\251' // "©"
'\xA9' // "©"
'\u00A9' // "©"

'\172' === 'z' // true
'\x7A' === 'z' // true
'\u007A' === 'z' // true
```

#### base64转码

btoa\(\)：字符串 OR 二进制数转化为 base64值

atob\(\)：上述操作的逆向

这两个方法不适合非ASCII码的字符，会报错。

```js
var string = 'Hello World!';
btoa(string) // "SGVsbG8gV29ybGQh"
atob('SGVsbG8gV29ybGQh') // "Hello World!"

// 不适用非 ASCII 码字符
btoa('你好')
VM756:1 Uncaught DOMException: Failed to execute 'btoa' on 'Window': The string to be encoded contains characters outside of the Latin1 range.

// 插入中间过程，适配非 ASCII 码字符转化
function b64Encode(str) {
  return btoa(encodeURIComponent(str));
}

function b64Decode(str) {
  return decodeURIComponent(atob(str));
}

b64Encode('你好') // "JUU0JUJEJUEwJUU1JUE1JUJE"
b64Decode('JUU0JUJEJUEwJUU1JUE1JUJE') // "你好"
```

### 对象

#### 对象的引用

* 不同变量名指向同一个对象，则他们都是这个对象的引用，通过其中一个变量名修改对象属性值，另一个变量名获取的相关属性值同样改变
* 对其中一个变量名重新赋值，相当于断掉与原对象的关联
* 对于原始数据类型为值的复制

```
var o1 = {};
var o2 = o1;
o1.a = 1;
o2.a;
<= 1

o2 = 1;
o1.a = 2;
o2.a;
<= undefined
o2
<= 1

var x = 999;
var y = x;
x = 198;
y
<= 999
```





