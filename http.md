### 001.网络七层模型

[网络七层模型（四层模型）及其区别](https://juejin.im/post/6844903939918266382)

### 002.三次握手，四次挥手

[TCP 三次握手 与 四次挥手](https://juejin.im/post/6844903888529653767)

### 003.从输入一个网址到看到一张网页，经历了什么？

[从输入一个网址到浏览器显示页面的全过程详细分析](https://juejin.im/post/6844903888483516430)

### 004.HTTP的请求与响应

- 请求：
  - 请求行，GET/HTTP/1.1
  - 请求头，非常多
  - 请求正文，扔给服务器的数据
- 响应：
  - 响应行，HTTP/1.1 200 OK
  - 响应头，非常多
  - 响应正文，服务器扔给客户端的数据

### 005.HTTP状态码

- 1xx
  - 101（双向通信）
- 2xx
  - 200（成功）
  - 204（没有响应体）
  - 206（断点续传）
- 3xx
  - 301（永久重定向）
  - 302（临时重定向）
  - 304（缓存）
- 4xx
  - 401（没有权限）
  - 403（登陆了没有权限）
  - 404（找不到对应的资源）
  - 405（请求方法不存在，不支持）
- 5xx
  - 502（负载均衡）

### 006.HTTP中的请求方法（8种）

[HTTP协议简介](https://juejin.im/post/6844903888563224583)

### 007.HTTP优化策略（博客）

压缩和缓存
 [HTTP前端性能优化(压缩与缓存)](https://juejin.im/post/6844903940316725255)

### 008.HTTP中的头（重点）

- 请求头：
  - `accept-encoding` 告诉服务器，我接收的数据支持压缩格式
  - `if-modified-since` 对比缓存  修改时间
  - `if-none-match` 摘要缓存  和`Etag`配对使用的
  - `user-agent` 不同设备自动带上这个头   判断什么样的设备，重定向到不同项目
- 响应头：
  - `Content-Type`  告诉浏览器  我给你的内容的类型
  - `Content-Encodin`g  告诉浏览器  我给你的内容的压缩格式
  - `Cache-Control` 强制缓存  告诉浏览器，你多长时间之间，不要来访问我
  - `Expires`  强缓   告诉浏览器，你多长时间之间，不要来访问我
  - `Last-Modified` 对比缓存 和 `if-modified-since` 配对使用
  - `Etag`   根据摘要做缓存   和 `if-none-match` 配对使用
  - `Lotaion`  重定向到 某个地方

### 009.HTTP中的代理

### 010.http和https有什么不同？

- https：是以安全为目标的HTTP通道，简单讲是HTTP的安全版本，通过SSL加密
- http：超文本传输协议。是一个客服端和服务器端请求和应答的标准（tcp）,使浏览器更加高效，使网络传输减少

### 011.localStorage, sessionStorage, cookie, session有什么区别？

- localStorage 不能跨域存取   最大存5M   超过5M的数据就会丢失   在发送请求时，不会带上localStorage
- sessionStorage 当浏览器关闭时，里面的数据就丢失
- cookie 服务器种植的，每次请求都会带上cookie，不安全，解决无状态问题，最多4K，浪费流量
- session 基于cookie  保存在服务器（内存，入库） 相对安全

前后端分离（前端调后端api接口）开发的：cookie，**主流：session 或 JWT**

[理解cookie、session、localStorage、sessionStorage的关系与区别](https://juejin.im/post/6844903975800537096)

### 012.从输入一个网址到浏览器显示页面的全过程？

1.DNS解析，找到IP地址
 2.根据IP地址，找到对应的服务器
 3.建立TCP连接(里面有个 三次握手)
 4.连接建立后，发出HTTP请求
 5.服务器根据请求作出HTTP响应
 6.浏览器得到响应内容，进行解析与渲染，并显示
 7.断开连接(四次挥手)

[从输入一个网址到浏览器显示页面的全过程详细分析](https://juejin.im/post/6844903888483516430)

### 013.简单说一下三次握手与四次挥手，为什么一个三次，一个四次？

[TCP 三次握手 与 四次挥手](https://juejin.im/post/6844903888529653767)

### 014.说一下web缓存？

1.web缓存就是存在于客户端与服务器之间的一个副本、当你第一个发出请求后，缓存根据请求保存输出内容的副本
 2.缓存的好处
 （1）减少不必要的请求
 （2）降低服务器的压力，减少服务器的消耗
 （3）降低网络延迟，加快页面打开速度（直接读取浏览器的数据）

### 015.常见的web安全及防护原理？

- sql注入原理：是将sql代码伪装到输入参数中，传递到服务器解析并执行的一种攻击手法。
- XSS（跨站脚本攻击）：往web页面插入恶意的html标签或者js代码。
- CSRF(跨站请求伪装）：通过伪装来自受信任用户的请求