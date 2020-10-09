# Blob

- <https://developer.mozilla.org/en-US/docs/Web/API/Blob>

Binary Large Object 二进制大对象

Blob 表示一个不可变的原始数据类文件对象。

可以作为文本或二进制数据读取，也可转换成 `ReadableStream` 并使用其方法处理数据。

文件 `File` 接口基于 Blob

## 构造函数

- `Blob()`
  - `var newBlob = new Blob(array, options)`
  - 返回一个新的 `Blob` 对象
  - 其内容为参数数组 `array` 中给定的值串联组成。
  - `options.type` - 指定数据的 MIME 类型 = `""`
  - `options.endings` - 指定文本数据中换行符 `\n` 的处理方式
    - `transparent` - 保持原样
    - `native` - 

