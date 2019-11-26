# EventTarget

- <https://developer.mozilla.org/en-US/docs/Web/API/EventTarget>

事件目标接口 `EventTarget` 是一个由对象实现的 DOM 接口，这些对象可以接收事件并且可能会有对应的监听器。

`Element`, `document`, `window` 是最常见的事件目标，但是其他对象也可以是事件目标，比如
`XMLHttpRequest`, `AudioNode`, `AudioContext` 等等。

## Constructor

- `EventTarget()`
  - 创建一个新的 `EventTarget` 对象实例。

## Methods

- `EventTarget.addEventListener()`
- `EventTarget.removeEventListener()`
- `EventTarget.dispatchEvent()`

