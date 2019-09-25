# :root

- <https://developer.mozilla.org/en-US/docs/Web/CSS/:root>

CSS 伪类选择器 `:root` 匹配文档的根元素。

对于 HTML 来说 `:root` 表示 `<html>` 元素，
除了优先级更高之外，作用与 `html` 选择器相同。

```css
:root {
  background: yellow;
}
```

### 语法

```css
:root { /* ...rules */ }
```

### 示例

`:root` 选择器常用于声明全局 CSS 变量

```css
:root {
  --main-color: hotpink;
  --pane-padding: 6px 42px
}
```


### 参考

- <https://www.w3school.com.cn/cssref/selector_root.asp>
- <http://www.runoob.com/cssref/sel-root.html>
- <http://css.doyoe.com/selectors/pseudo-classes/root.htm>
