## 前端 Js 获取模板变量的值

* 通过隐藏 input 方式获取

```html
<input type="hidden" id="foo" value="{:U('/controller/action/xxx')}">

<script>
    ...
    const val = $('#foo').val();
    console.log('val: ', val);
    ...
</script>
```



