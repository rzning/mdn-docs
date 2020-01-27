# env()

- <https://developer.mozilla.org/en-US/docs/Web/CSS/env>


CSS 函数 `env()` 将用户代理定义的环境变量的值插入到 CSS 中，
其方式与 [var()] 函数和自定义属性 ( [custom properties] ) 类似。

环境变量的作用域是整个文档，而自定义属性的作用域是声明它们的元素。

最初由 iOS 浏览器提供，用于允许开发人员将其内容放置在视口的安全区域中，
该规范中定义的 `safe-area-inset-*` 值可用于确保内容即使在非矩形的视区中也可以完全显示。

## 示例

```html
<meta name="viewport" content="viewport-fit=cover" />

<style>
  body {
    padding:
      env(safe-area-inset-top, 20px)
      env(safe-area-inset-right, 20px)
      env(safe-area-inset-bottom, 20px)
      env(safe-area-inset-left, 20px);
  }
</style>
```

其中的页面文档元数据 [`<meta>`][meta] 元素的 `viewport` 用于提供有关视口初始大小的提示信息，仅供移动设备使用。

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
```

CSS 用于设置初始视口的 [@viewport] 规则中的 [viewport-fit] 描述符 ( descriptor ) 用于控制文档在非矩形显示器上的显示。

`viewport-fit`
  - `auto` - 此值不影响初始布局视口，并且整个页面都是可见的
  - `contain` - 视口被缩放，以适合与显示屏内切的最大矩形
  - `cover` - 视图被缩放以填充设备显示
    - 此时强烈建议使用安全区域内嵌 `safe-area-inset-*` 变量，以确保重要的内容不会显示在屏幕之外。

在使用 [viewport-fit] 描述符时，必须记住并不是所有的设备显示都是矩形的，因此应该使用 `safe-area-inset-*` 变量。

## 语法

```css
env( <safe-area-inset-*> , <fallback-value>? )
```

- `safe-area-inset-*`
  - `safe-area-inset-top`
  - `safe-area-inset-right`
  - `safe-area-inset-bottom`
  - `safe-area-inset-left`

`safe-area-inset-*` 为四个定义了视口边缘内矩形的环境变量组成，
这样可以安全的放入内容，而不必担心在非矩形显示设备显示不全的问题。

- 对于矩形视口，比如电脑显示器，其值等于零。
- 对于非矩形显示器，比如圆形表盘，用户代理设置的四个值形成的矩形内所有内容可见。


[var()]: <https://developer.mozilla.org/en-US/docs/Web/CSS/var>
[custom properties]: <https://developer.mozilla.org/en-US/docs/Web/CSS/--*>
[meta]: <https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta>
[@viewport]: <https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport>
[viewport-fit]: <https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport/viewport-fit>

