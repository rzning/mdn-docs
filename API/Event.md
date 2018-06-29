# Event

- <https://developer.mozilla.org/en-US/docs/Web/API/Event>

`Event` 接口表示在 DOM 中发生的任何事件;
有些是用户生成的（如鼠标或键盘事件），
而另一些则是由 APIs 生成的（如表示动画已运行完毕的事件、视频已暂停、等等）。

---

## Interfaces based on Event

- AnimationEvent
- BlobEvent
- ErrorEvent
- FetchEvent
- InputEvent
- KeyboardEvent
- MessageEvent
- MouseEvent
- ProgressEvent
- StorageEvent
- SVGEvent
- TimeEvent
- TouchEvent
- TransitionEvent
- UIEvent
- WebGLContextEvent

## Constructor

- Event()

## Properties

- Event.bubbles
- Event.cancelBubble
- Event.cancelable
- Event.composed
- Event.currentTarget
- Event.deepPath
- Event.defaultPrevented
- Event.eventPhase
- Event.explicitOriginalTarget
- Event.originalTarget
- Event.returnValue
- Event.srcElement
- Event.target
- Event.timeStamp
- Event.type
- Event.isTrusted

## Methods

- Event.createEvent()
- Event.composePath()
- Event.initEvent()
- Event.preventDefault()
- Event.stopImmediatePropagation()
- Event.stopPropagation()

## Specifications

- <https://dom.spec.whatwg.org/#interface-event>

