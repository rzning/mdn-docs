# Service Worker API

- <https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API>

服务工作线程 Service workers 本质上是一个代理服务器 Proxy Servers

其目的之一是为了创造有效的离线体验，

拦截网络请求，并根据网络是否可用采取适当的操作。


## 概念和用法

Service Worker 是一个注册在指定 源 origin 和 路径 path 下的 事件驱动的 Worker 工作线程。

- 在单独 JavaScript 文件中定义，并独立运行，

- 可以控制它所关联的网页或网站。

- 拦截并修改（导航和资源）请求

- 以细粒度地方式缓存资源，

- 能够完全控制应用在某些情况下的行为，通常为网络不可用的情形。

### 独立线程

Service Worker 运行在 Worker 上下文，不能访问 DOM

与驱动应用的 主 JavaScript 线程 不同，它运行于其他线程，不会造成阻塞。

它被设计为完全异步的，因此一些诸如 同步的 XHR 和 localStorage 等 API 不能在 Service Worker 中使用。

出于安全原因 Service Worker 只运行在 HTTPS 之上。

### 注册

```js
/**
 * @param {string} scriptURL 脚本文件 URL
 * @param {Object} options 可选配置项
 * @param {USVString} options.scope 可控范围相对 URL
 * @return {Promise} ServiceWorkerRegistration
 */
ServiceWorkerContainer.register(scriptURL, options)
```

示例：

```js
navigator.serviceWorker.register('service-worker.js', { scope: './' })
.then((registration) => {
  document.querySelector('#status').textContent = 'success'
})
```

### 生命周期

1. 下载
2. 安装
3. 激活
