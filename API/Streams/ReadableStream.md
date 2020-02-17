# ReadableStream

- <https://developer.mozilla.org/en-US/docs/Web/API/ReadableStream>

Streams API 中的 `ReadableStream` 接口表示一个可读的字节数据流。

Fetch API 通过 `Response` 对象的 `body` 属性提供了 `ReadableStream` 的具体实例。

## Examples

```js
fetch('https//www.example.org/').then(response => {
  /**
   * @type {ReadableStreamDefaultReader<Uint8Array>}
   * @see {@link https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultReader}
   */
  const reader = response.body.getReader()
  /**
   * @type {ReadableStream}
   */
  const stream = new ReadableStream({
    /**
     * 在构造对象时立即调用此方法
     * @param {ReadableStreamDefaultController} controller
     */
    start (controller) {
      /** 用于处理每个数据块 */
      function push () {
        /**
         * @param {boolean} done
         * @param {Uint8Array} value
         */
        reader.read().then(({ done, value }) => {
          if (done) {
            controller.close()
            return
          }
          /**
           * 在关联流中对给定块进行排队
           * @see {@link https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamDefaultController/enqueue}
           */
          controller.enqueue(value)
          push()
        })
      }
      push()
    }
  })
  return new Response(stream, {
    headers: { 'Content-Type': 'text/html' }
  })
})
```
