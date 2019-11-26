# TouchEvent

- <https://developer.mozilla.org/en-US/docs/Web/API/TouchEvent>

`TouchEvent` 接口代表一个 `UIEvent` 表示当用户与触摸板表面接触的状态发生变化时触发。

该事件可以描述与屏幕的一个或多个触摸点，并可对移动、添加或删除触控点的检测支持。

- 每个触摸点由 `Touch` 对象表示，每个触控点都有其位置、大小和形状、压力大小、和目标元素来描述。

- 多个触摸点由 `TouchList` 表示。

```
Event <-- UIEvent <-- TouchEvent
```

## 构造方法 Constructor

- `TouchEvent()`
  - 创建一个 `TouchEvent` 对象

## 属性 Properties

此接口继承了其父接口 `UIEvent` 和 `Event` 的属性。

以下属性都是只读属性：

- `TouchEvent.altKey`
  - 布尔值，指示触摸事件触发时 alt 键是否被按下。
- `TouchEvent.changedTouches`
   - 一个触摸列表 `TouchList` 对象，存储了所有在前一次触摸事件到当前触摸事件之间状态发生改变的触摸点 `Touch` 对象。
- `TouchEvent.ctrlKey`
  - 布尔值，指示触摸事件触发时 ctrl 键是否被按下。
- `TouchEvent.metaKey`
  - 布尔值，指示触摸事件触发时 meta 键是否被按下。
- `TouchEvent.shiftKey`
  - 布尔值，指示触摸事件触发时 shift 键是否被按下。
- `TouchEvent.targetTouches`
  - 一个触摸列表 `TouchEvent` 对象，存储了当前目标元素上的所有触摸点 `Touch` 对象。
- `TouchEvent.touches`
  - 一个触摸列表 `TouchEvent` 对象，存储了当前触摸面板上的所有触控点 `Touch` 对象，无论是否在目标元素上或状态改变。
- *`TouchEvent.rotation`*
  - 表示触摸事件开始后的旋转角度大小。正值表示顺时针旋转。
- *`TouchEvent.scale`*
  - 表示触摸事件发生时两个触摸点间的距离缩放比率。

## 触摸事件类型 Touch event types

可以通过 `TouchEvent.type` 属性来确定当前触摸事件类型。

- `touchstart`
  - 触摸开始事件
- `touchend`
  - 触摸结束事件
- `touchmove`
  - 触摸移动事件
- `touchcancel`
  - 触摸中断事件

使用触摸事件时，应调用 `preventDefault()` 方法，以确保鼠标事件不会被触发。

