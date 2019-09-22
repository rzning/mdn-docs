# 跨域资源共享 CORS

> Cross-Origin Resource Sharing

- <https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS>
- <https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Access_control_CORS>

## HTTP 访问控制

CORS ( Cross-Origin Resource Sharing 跨域资源共享 ) 是一种机制 ( mechanism ) ，
它使用附加的 [HTTP] 头来告知浏览器，以使一个 Web 应用程序在一个 [origin] 源运行，
并允许访问来自不同源 ( [origin] ) 服务器上的指定资源。

当一个 Web 应用程序请求来自不同源 ( [origin] ) 的资源时，将发起一个 跨域 HTTP 请求 ( cross-origin HTTP request ) 。

不同源包括：域名 ( domain ) 、协议 ( protocol ) 或 端口 ( port ) 的不同。

例如在 `https://domain-a.com` 站点，试图通过一个 [XHR] 请求 `https://domain-b.com/data.json` 文件。

### 浏览器跨域限制

出于安全原因，浏览器限制了从脚本发起的 跨源 HTTP 请求 ( cross-origin HTTP requests ) 。

例如 [XHR] 和 [Fetch API] 遵循 同源策略 ( [same-origin policy] )

只意味着，使用这些 API Web 应用程序只能从加载应用程序的同源 ( [origin] ) 请求 HTTP 资源，
除非来自其他 [origin] 的响应 ( response ) 报文包含正确的 CORS 响应头。

![CORS_principle](https://mdn.mozillademos.org/files/14295/CORS_principle.png)


[HTTP]: <https://developer.mozilla.org/zh-CN/docs/Glossary/HTTP>
[Origin]: <https://developer.mozilla.org/zh-CN/docs/Glossary/Origin>
[XHR]: <https://developer.mozilla.org/zh-CN/docs/Glossary/XHR_(XMLHttpRequest)>
[Fetch API]: <https://developer.mozilla.org/zh-CN/docs/Web/API/Fetch_API>
[same-origin policy]: <https://developer.mozilla.org/zh-CN/docs/Web/Security/Same-origin_policy>
