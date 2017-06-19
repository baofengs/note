## Js 全局对象使用总结

## encodeURI/decodeURI

* \[encodeURI\]\([https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global\_Objects/encodeURI](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI%29%29\)

  * 不转换字符

  | 类型 | 字符 |
  | :--- | :--- |
  | 保留字符 | ; , / ? : @ & = + $ |
  | 非转义的字符 | 字母 数字 - \_ . ! ~ \* ' \( \) |
  | 数字符号 | \# |

```javascript
let link = 'https://www.baidu.com/s?ie=UTF-8&wd=js%20%E5%85%A8%E5%B1%80%E5%87%BD%E6%95%B0';
// decodeURI: decodeURI() 函数可对 encodeURI() 函数编码过的 URI 进行解码。
const decoded = decodeURI(link);

<= "https://www.baidu.com/s?ie=UTF-8&wd=js 全局函数"

// encodeURI: encodeURI() 函数可把字符串作为 URI 进行编码
const encoded = encodeURI(decoded);
<= "https://www.baidu.com/s?ie=UTF-8&wd=js%20%E5%85%A8%E5%B1%80%E5%87%BD%E6%95%B0"
```



