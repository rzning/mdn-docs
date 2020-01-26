# EventTarget.addEventListener()

- [/docs/Web/API/EventTarget/addEventListener][addEventListener()]


`EventTarget.addEventListener()` 方法将指定的监听器注册到 [EventTarget] 上，
当该对象触发指定的事件时，指定的回调函数就会被执行。

只要将指定的事件传递到目标 [EventTarget] 对象，就会调用 [addEventListener()] 方法设置的回调函数。

`addEventListener()` 的工作方式是将实现 [EventListener] 接口的函数或对象添加到（用于调用它的 [EventTarget] 上的指定事件类型的）事件监听器列表中。


## Syntax

```js
target.addEventListener(type, listener [, options]);
target.addEventListener(type, listener [, useCapture]);
```

参数：

- `type`
  - 表示要侦听的 [事件类型](Events) 的大小写敏感字符串。
- `listener`
  - 接收通知的监听器
  - 通知 : 实现 [Event] 接口的对象
  - 监听器 : 实现 [EventListener] 接口的对象或方法
- `options`
  - 一个描述事件监听器的可选参数对象
  - `capture` - 使能在事件捕获阶段触发
  - `once` - 使能只触发一次，监听器被调用后自动移除
  - `passive` - 一个布尔值
    - 如果为真，表示监听器指定的函数永远不会调用 [preventDefault()]
    - 若侦听器仍然调用了 [preventDefault()] 方法，那么用户代理（客户端）将不执行任何操作，只生成一个控制台警告。
- `useCapture`
  - 使能监听器在捕获阶段触发
  - 默认 `false` 在冒泡阶段触发

> 事件流包含三个阶段：事件捕获阶段、处于目标阶段、事件冒泡阶段。


[EventTarget]: <https://developer.mozilla.org/en-US/docs/Web/API/EventTarget>
[addEventListener()]: <https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener>
[EventListener]: <https://developer.mozilla.org/en-US/docs/Web/API/EventListener>
[Events]: <https://developer.mozilla.org/en-US/docs/Web/Events>
[Event]: <https://developer.mozilla.org/en-US/docs/Web/API/Event>
[preventDefault()]: <https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault>
