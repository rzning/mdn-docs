# var()

- <https://developer.mozilla.org/en-US/docs/Web/CSS/var>

CSS 函数 `var()` 用于获取指定自定义属性（有时称之为 CSS 变量）的值，并作用于当前位置。

```css
.top-bar {
  color: var(--header-color, blue);
}
```

`var()` 函数不能作用于属性名、选择器或除属性值之外的任何内容。

### 语法

```
var( <custom-property-name> , <declaration-value>? )
```

- `<custom-property-name>` 自定义属性名
  - 自定义属性的名称，由以两个破折号 `--` 开头的标识符表示，大小写敏感。
- `<declaration-value>` ( 可选 ) 声明值，回退值，默认值
  - 回退值，在第一个参数引用的自定义属性无效时，则该函数使用此值。

### 示例

`var()` 函数的第一个 `,` 后面的所有内容都作为

```css
:root {
  --box-border: 1 solid black;
}

.component {
  border: var(--box-border, 2 solid gray)
}
```

CSS 自定义属性具有继承和级联特性。

```css
:root {
  --text-color: blue;
}

.component .text {
  color: var(--text-color); /* pink */
}

.component {
  --text-color: pink;
}
```

### 参考

- [使用 CSS 定义属性（变量） - CSS | MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [CSS 变量教程 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2017/05/css-variables.html)
