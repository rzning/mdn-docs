# void operator

- [JavaScript/Reference/Operators/void][void]

[void]: <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/void>

[void] 运算符 对给定的 `expression` 表达式进行求值，并返回 `undefined`

## 语法 Syntax

```
void expression
```

## 描述 Description

`void` 操作符通常指用于获取 `undefined` 的原始值。

- 通常使用 `void(0)` 相当于 `void 0`

- 也可以使用全局变量 `undefined` 来代替，前提是它没有被分配到一个非默认值。


在使用过程中，应注意 `void` 操作符的优先级，例如下面例子：

```js
void 2 == '2'   // (void 2) == '2' , returns false
void (2 == '2') // void true, returns undefined
```

## 立即执行的函数表达式

使用 `void` 运算符可以让 Javascript 引擎将 `function` 关键字识别为一个表达式，而非一个声明。

```js
void function func () {
  // ...
}();
```

## Javascript URIs

当浏览器访问一个 `javascript:` URI 时，将会执行 URI 中的代码，并用返回值替换页面内的内容，除非其返回值是 `undefined` 。

- `void` 运算符可以用于返回 `undefined`

```html
<a href="javascrpt:void(0);">
  点击此链接不做任何事情
</a>

<a href="javacript:void(document.body.style.backgroundColor='green')">
  点击此链接页面背景将变为绿色
</a>
```

不推荐使用 `javascript:` 伪协议，推荐使用为链接元素添加事件处理函数。

## 在箭头函数中避免泄漏 Non-leaking Arrow Functions


```js
button.onclick = () => void doSomething();
```

避免当 `doSomething()` 方法的返回值从 `undefined` 变为 `ture` 时，不会改变此代码的行为。

