# MutationObserver

- <https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver>

`MutationObserver` 接口提供了对 DOM 树所做更改的监听能力。

## 构造函数

- ### `MutationObserver()`
  - 创建并返回一个新的 `MutationObserver` 观察器对象。
  - `const observer = new MutationObserver(callback)`
  - `callback` 回调函数，在所观察的节点或子树的每次 DOM 变动时触发。
    - `(mutationList, observer) => void`
    - 回调函数第一个参数为 DOM 变化描述对象 `MutationRecord` 数组。
    - 回调函数第二个参数为当前观察器实例对象。


## 方法

- `observe(target, options)`
  - 观察指定 DOM 节点变化。

- `disconnect()`
  - 取消观察。

- `takeRecords()`
  - 获取所有待处理变更记录，并清空队列。

## 示例

```js
const targetNode = document.getElementById('targetElementId')

// 新建观察器实例
const observer = new MutationObserver((mutationsList, observer) => {
  for (const mutation of mutationsList) {
    switch (mutation.type) {
      case 'attributes': {
        // 属性变化
        break
      }
      case 'childList': {
        // 子节点树变化
        break
      }
      case 'characterData': {
        // 字符数据变化
        break
      }
    }
  }
})

// 观察指定元素节点
observer.observe(targetNode, {
  attributes: true,
  childList: true,
  characterData: true
})

// 停止观察
observer.disconnect()
```