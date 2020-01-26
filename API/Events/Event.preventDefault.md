# Event.preventDefault()

- [docs/Web/API/Event/preventDefault][preventDefault()]

[Event] 接口的 [preventDefault()] 方法将告诉用户代理（如浏览器客户端）阻止对触发事件的默认操作。

事件将继续传播，除非它的事件监听器调用 [stopPropagation()] 或 [stopImmediatePropagation()] 方法，其中任何一个都会立即终止传播。

可以使用 [Event.cancelable] 来检查该事件是否支持取消，为不可取消的事件调用 [preventDefault()] 将没有效果。

## Syntax

```js
event.preventDefault();
```

## Examples

```html
<form>
  <label for="target">Checkbox:</label>
  <input type="checkbox" id="target">
</form>
<script>
  document.querySelector('target')
    .addEventListener('click', function (event) {
      // 阻止浏览器选中复选框
      event.preventDefault()
    }, false)
</script>
```

[Event]: <https://developer.mozilla.org/en-US/docs/Web/API/Event>
[Event.cancelable]: <https://developer.mozilla.org/en-US/docs/Web/API/Event/cancelable>
[preventDefault()]: <https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault>
[stopPropagation()]: <https://developer.mozilla.org/en-US/docs/Web/API/Event/stopPropagation>
[stopImmediatePropagation()]: <https://developer.mozilla.org/en-US/docs/Web/API/Event/stopImmediatePropagation>
