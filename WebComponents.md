# Web Components

- <https://developer.mozilla.org/en-US/docs/Web/Web_Components>

Web Components 是一套不同的技术，
允许您创建可重用的定制元素（它们的功能封装在您的代码之外），
并且在你的 Web 应用中使用它们。

- Interfaces
  - CustomElementRegistry
  - HTMLSlotElement
  - HTMLTemplateElement
  - ShadowRoot
  - DocumentOrShadowRoot
  - Slotable
- Properties
  - Element.shadowRoot
  - Element.slot
  - Event.composed
  - Event.composedPath
  - Node.isConnected
  - Window.customElements
- Methods
  - Document.createElement()
  - Element.attachShadow()
  - Node.getRootNode()
- Events
  - slotchange

---

## Concepts and usage 概念和用法

Web Components 由四项主要技术组成，它们可以一起使用来创建封装功能的定制元素，
可以在你喜欢的任何地方重用，不必担心代码冲突。

Custom elements | Shadow DOM | HTML Templates | HTML Imports
-|-|-|-
自定义元素 | 影子 DOM | HTML 模板 | HTML 导入

### Custom elements

- 允许你定义其行为，然后在用户界面中使用它们。

### Shadow DOM

- 用于功能封装，与主文档分开呈现，并控制其关联的功能。
通过这种方式，您可以保持元素的功能私有，而不用担心与文档的其他部分发生冲突。

### HTML templates

- `<template>` 和 `<slot>` 标签元素，可以编写不在呈现页面中显示的标记模板。
  并且它们可以做为 custom element 结构的基础被多次重用。

### HTML Imports

- 使用 Custom element 最简单的重用方式是将其细节定义在单独的文件，
然后使用导入机制将其导入到实际想使用它的页面中。

实现 Web Component 的基本方法通常如下所示：

1. 创建一个类，在其中使用 ECMAScript 2015 类语法指定你的 web component 功能。
2. 注册你的 custom element 使用 `CustomElementRegistry.define()` 方法。
3. 如果需要，可将一个 shadow DOM 添加到 custom element 上，使用 `Element.attachShadow()` 方法。
4. 如果需要，使用 `<template>` 和 `<slot>` 定义一个 HTML template 并使用常规 DOM 方法克隆模板，将其附加到你的 shadow DOM 中。
5. 在页面任何使用自定义元素，就像使用常规 HTML 元素一样。

## Tutorials 教程

- Using custom elements
- Using shadow DOM
- Using templates and slots

---

# Using custom elements 使用自定义元素

- <https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements>

Web Components 标准一个非常重要的特性是，使开发者能够在 HTML 页面中创建自定义元素来封装自己的功能，
而不是必须使用一堆嵌套的元素来实现相同的功能。

## 概述

在 Web 文当中自定义元素的控制器是 `CustomElementRegistry` 对象。

该对象允许你在页面中注册一个自定义元素，并返回相关注册信息等。

```js
/**
 * 定义一个自定义元素
 * @param {String} name 自定义元素名，自定义元素名称必须包含连字符。
 * @param {Class} constructor 自定义元素的构造方法，用于定义元素行为。
 * @param {Object} options 可选，配置对象，目前只有一个 `extends` 选项。
 * @param {String} options.extends 指定所创建元素继承自哪个内置元素。
 * @return void
 */
customElementRegistry.define(name, constructor, options)
```

下面例子定义了一个继承自 `<p>` 元素的自定义元素 `word-count`。

```js
class WordCount extends HTMLParagraphElement {
  constructor() {
    super();
    //...
  }
}
customElements.define('word-count', WordCount, { extends: 'p' });
```
```html
<p is="word-count"></p>
```

你可以创建两种类型的自定义元素：

### Autonomous custom element

独立的元素，不会继承自内置 HTML 元素。

可以直接写成标 HTML 签形式使用，如 `<popup-info>`，
也可以调用 `document.createElement('popup-info')` 方法使用。

### Customized built-in elememt

定制的内置元素，此类元素继承并扩展了内置 HTML 元素。

必须使用所继承的基本元素标签，并通过 `is` 属性指定自定义元素名称，如 `<p is="word-count">`，
或者调用 `document.createElement('p', { is: 'word-count' })` 方法使用。

## Simple Examples 简单示例



