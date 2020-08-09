# 2020年8月第1周 - 智云健康前端技术每周文摘

## 文摘目录

* [原创](#原创)
* [翻译](#翻译)
* [文章与新闻](#文章与新闻)
* [推荐库](#推荐库)
* [每周一练](#每周一练)

## 原创

- [Vue2.6企业级项目结构推荐](https://juejin.im/post/6857028645534793735)：一个适合迭代大项目的项目结构
- [纯CSS实现水平并垂直居中的15种方式](https://juejin.im/post/6856579922148884488)：总有你想不到的方式
- [三行CSS为掘金添加暗黑模式支持](https://juejin.im/post/6858448795949236231)：快速实现暗黑模式的傻瓜式操作

## 翻译

- [为什么不需要在Vue3中使用Vuex](https://juejin.im/post/6856718746694713352)：Medium热门Vue文章翻译

## 文章与新闻

- [跨越嵌入式到云端的新型容器：WebAssembly Micro Runtime](https://www.infoq.cn/article/PjjSD5W6XzT5X6Fw1ZRc)："把WASM当docker用"，参考文章：[去中心化计算的未来：通过 RPC 从微服务过渡到 WASM](https://juejin.im/post/6844904029525377037)
- [使用带动态导入的ES模块实现微前端](https://blog.bitsrc.io/using-es-modules-with-dynamic-imports-to-implement-micro-frontends-7c840a38890e)：通过System.js+动态导入实现微前端
- [像资深前端工程师一样使用Chrome DevTools](https://medium.com/javascript-in-plain-english/use-chrome-devtools-like-a-senior-frontend-developer-99a4740674)：DevTools小技巧
- [使用Service Work重构现代应用的五种方式](https://blog.bitsrc.io/how-service-workers-will-reshape-your-modern-web-apps-c0cc85b8a287)：Service Work的五种应用场景

## 推荐库

- [Ink v3.0.1](https://github.com/vadimdemedes/ink)：使用React开发交互式命令行，近期发布的Ink3提供了一系列强大的Hooks，如：`useInput`读取用户输入，`useStdin`、`useStdout`访问标准输入输出流等；同时改写了`Static`等组件，提升其性能与稳定性；Ink3支持使用React Devtools进行调试。 
- [Next.js v9.5.0](https://nextjs.org/blog/next-9-5)：React服务端渲染框架，9.5可选择使用Webpack5编译、构建
- [Attain v1.0.6](https://github.com/aaronwlee/Attain)：一个类express的`Deno`web框架
- [tinykeys v1.0.3](https://github.com/jamiebuilds/tinykeys)：一个键盘按钮的绑定库，支持单独使用或与React hooks结合使用
- [OpenRPC](https://open-rpc.org/)：OpenRPC定义了一套与编程语言无关的[JSON-RPC 2.0](https://www.jsonrpc.org/specification)协议

## 每周一练

### 过滤多叉树

在给定的多叉树中过滤指定关键词，但子级包含该关键词时，父级也应该保留下来。

#### 示例：

```js
* 测试1
 * 测试2
  * 测试3
   * 需要过滤掉
* 测试4
 * 这个是父元素
  * 测试5
```
当我输入“测试”时，进行模糊匹配，需要将所有包含“测试”的节点都列出来。结果是这样的。
```js
* 测试1
 * 测试2
  * 测试3
* 测试4
 * 这个是父元素
  * 测试5
```
只要是父元素下面得子元素含有“测试”这个字符串，不管本身是否含有这个字符串都必须保留。

#### 要求：
写出少于O(2n)时间复杂度的算法

```
function filterTree(node, keyword) {}
```
