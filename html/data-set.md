### HTML 中自定义数据属性

形如：data-\*

示例：

```js
<div id="user" data-id="1234567890" data-user="johndoe" data-date-of-birth>John Doe
</div>

var el = document.querySelector('#user');

// el.id === 'user'
// el.dataset.id === '1234567890'
// el.dataset.user === 'johndoe'
// el.dataset.dateOfBirth === ''

el.dataset.dateOfBirth = '1960-10-03'; // set the DOB.

// 'someDataAttr' in el.dataset === false

el.dataset.someDataAttr = 'mydata';
// 'someDataAttr' in el.dataset === true
```

MDN：[https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/dataset](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLElement/dataset)

codePen：[https://codepen.io/SanBf/pen/ZyVrWg](https://codepen.io/SanBf/pen/ZyVrWg)

