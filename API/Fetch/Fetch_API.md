# Fetch API

- <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API>

Fetch API  提供了一个用于获取资源的接口。

## 概念和用法

Fetch 提供了对 Request 和 Response 及其他与网络请求相关的对象的通用定义。

## Fecth Interfaces

- `WindowOrWorkerGlobalScope.fetch()`
  - 调用此方法获取相应资源

- `Headers`
  - 头信息对象，请求或响应头。
  - `Headers()`
    - 创建一个新的 `Headers` 对象
    - `var myHeaders = new Headers();`
  - `myHeaders.append(name, value);`
    - 追加 `header` 值
  - `myHeaders.get(name);`
    - 返回指定 `header` 的所有值的 `ByteString` 字符串序列，若未拿到值则返回 `null`
  - `myHeaders.set(name, value);`
    - 设置指定 `header` 值，若之前有值则将会被覆盖
  - `myHeaders.delete(name);`
    - 删除指定 `header`
  - `myHeaders.has(name);`
    - 判断是否含有指定的 `header`
  - `myHeaders.entries();`
    - 返回一个 `iterator` 允许遍历此对象中包含的所有 key/value pairs
  - `myHeaders.keys();`
    - 返回所有 key 组成的 `iterator`
  - `myHeaders.values()`
    - 返回所有 value 组成的 `iterator`

- `Request`
  - 资源请求对象

- `Response`
  - 请求的响应对象

## Fecth mixin

- `Body`
  - 请求或响应体对象
  - 提供与 response/request 的 body 相关的方法，允许声明其内容类型及其处理方式。
  - `Body.body`
    - 只读，一个简单的 getter 用于暴露 body 内容的 `ReadableStream` 可读流。
    - `var stream = response.body;`
  - `Body.bodyUsed`
    - 只读布尔值，只是该 body 是否已经被读取
    - 如调用 `blob()` 方法后 `bodyUsed` 将由 `false` 变为 `true`
  - `Body.arrayBuffer()`
    - 获取响应流并将其读取到完成。
    - 返回一个使用 `ArrayBuffer` 解析的 Promise
    - 也就是返回一个 Promise 对象，其中 resolve 了一个 `ArrayBuffer` 对象
    - `response.arrayBuffer().then(buffer => { ... })`
  - `Body.blob()`
    - 获取一个 `Response` 流，并读取到完成。
    - 返回一个使用 `Blob` 解析的 Promise 对象
    - `response.blob().then(myBlob => { ... })`
  - `Body.formData()`
    - 获取响应流并读取到完成。
    - 返回使用 `FormData` 对象解析的 Promise 对象
  - `Body.json()`
    - 接收一个响应流，并将其读取完成。
    - 返回一个 Promise 对象，其解析 resolve 结果是将结果作为 JSON 解析。
    - `response.json().then(data => { ... })`
  - `Body.text()`
    - 获取响应流并将其读取到完成。
    - 返回一个使用 `USVString` 解析的 Promise
    - 响应总是使用 UTF-8 解码。
  

