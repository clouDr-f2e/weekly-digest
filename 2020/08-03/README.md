# 2020年8月第3周 - 智云健康前端技术每周文摘

## 文摘目录

* [原创](#原创)
* [文章与新闻](#文章与新闻)
* [推荐库](#推荐库)
* [每周一练](#每周一练)

## 原创

- [前端监控平台系列：JS SDK](https://juejin.im/post/6862559324632252430)：手摸手教你写SDK
- [JS引擎（一）：JS中的JIT与基本执行逻辑](https://juejin.im/post/6863269040300032008)：搞懂JIT的执行逻辑

## 文章与新闻

- [使用纯Rust构建一个单页应用](http://www.sheshbabu.com/posts/rust-wasm-yew-single-page-application/)
- [如何学习一个框架？](https://xie.infoq.cn/article/99fee64fec648bce7fc4381f4)
- [图解 JavaScript——代码实现六种异步方案](https://xie.infoq.cn/article/578257b224a24300c6e0b025b)

## 推荐库

- [React v17.0 RC](https://reactjs.org/blog/2020/08/10/react-v17-rc.html)：React17来了
- [NPM v7 beta](https://blog.npmjs.org/post/626173315965468672/npm-v7-series-beta-release-and-semver-major)：NPM7测试版来了
- [reactant v0.3.2](https://github.com/unadlib/reactant)：像angular一样使用React
- [teki](https://github.com/philipnilsson/teki)：TS极小的路由解析器

## 每周一练

### 要求

实现一个批量请求函数，支持最大并发量，每当有一个请求返回，就留下一个空位，可以增加新的请求，所有请求完成后，返回一个promise，结果按照 urls 里面的请求顺序依次打出。

```js
/**
 * 
 * 实现一个批量请求函数 multiRequest(urls, maxNum)
 * @param {Array} urls 异步请求
 * @param {Number} maxNum 并发的最大数量
 * @param {Function} singleFetchOverCallback 单个执行完执行的回调函数，异步返回的数据作为入参
 */
function multiRequest(urls, maxNum, singleFetchOverCallback) {
}
```

#### 示例：

```js
/**
 * 模拟异步请求
 * @param {Number} delay 延迟秒数
 * @param {Any} result 返回数据
 */
function setTimeoutWithParam(delay, result) {
  return () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve(result);
      }, delay);
    });
  };
}
multiRequest(
  [
    setTimeoutWithParam(2000, 3),
    setTimeoutWithParam(1000, 1),
    setTimeoutWithParam(2000, 2),
    setTimeoutWithParam(4000, 4),
    setTimeoutWithParam(5000, 5),
    setTimeoutWithParam(6000, 6),
  ],
  5,
  res => {
    if (res === 5) {
      // 增加一个异步请求
      multiRequest.prototype.addUrl(setTimeoutWithParam(100, 7));
    }
    console.log('single', res);
  }
).then(res => {
  console.log('all over', res);
});

```

#### 打印结果：

```js
single 1
single 3
single 2
single 4
single 5
single 7
single 6
all over [
  1, 3, 2, 4,
  5, 7, 6
]
```
