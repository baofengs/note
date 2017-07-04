### INPUT

### JS 操作

获取value

```js
// <input id="foo" type="text"/>
const value = document.querySelector('#foo').value;
```

onchange

* 触发时机:

  * &lt;input type="radio"&gt; 和 &lt;input type="checkbox"&gt; 的默认选项被修改时（通过点击或者键盘事件）;
  * 当用户完成提交动作时 \(例如：点击了 &lt;select&gt;中的一个选项，从 &lt;input type="date"&gt;标签选择了一个日期，通过 &lt;input type="file"&gt;标签上传了一个文件，等 \);

  * 当标签的值被修改并且失焦后，但并未进行提交 \(例如：对&lt;textarea&gt; 或者&lt;input type="text"&gt;的值进行编辑后。\).

```js
**FOR INPUT type="text"**  点击回车触发事件 OR 失焦
// <input id="foo" type="text" onchange="chageHandler(event)" />
function changeHandler(event) {
    console.log(evnet.target.value);
}

** FOR INPUT type="select"** 切换选项
<html>
  <head>
    <title>Example: Change event on a select</title>
    <script type="text/javascript">
      function changeEventHandler(event) {
        alert('You like ' + event.target.value + ' ice cream.');
      }
    </script>
    </head>
    <body>
        <label>Choose an ice cream flavor: </label>
        <select size="1" onchange="changeEventHandler(event);">
            <option>chocolate</option>
            <option>strawberry</option>
            <option>vanilla</option>
        </select>
    </body>
</html>
```

### 样式自定义

禁用自动补全

* autocomplete 属性：on/off

```
<input type="text" autocomplete="on/off"/>
```

边框处理

```
input {
    border: none;
    border-bottom: 1px solid #ccc;
}
// 禁用聚焦时的边框
input:focus {
    outline: none;
    border-bottom-color: #fff;
}
```

最终效果：

### 



