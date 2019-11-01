# Error

- <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error>

Error 构造器用于创建一个错误对象。

当运行代码有错误发生时，将创建并抛出一个 Error 实例对象。

```js
try {
  throw new Error('Whoops!')
} catch (err) {
  console.log(`${err.name}: ${err.message}`)
}
```


## 错误类型

type | description
-|-
`EvalError` | 与 `eval()` 相关的错误
`InternalError` | 内部错误，JS 引擎内部错误，如无限递归
`RangeError` | 范围错误，数值变量或参数超出其有效范围
`ReferenceError` | 引用错误，引用了未被定义的变量
`SyntaxError` | 语法错误
`TypeError` | 类型错误，变量或参数的值为非预期类型
`URIError` | URL 不合法
