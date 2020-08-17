# 2020年8月第2周 - 智云健康前端技术每周文摘

## 文摘目录

* [原创](#原创)
* [翻译](#翻译)
* [文章与新闻](#文章与新闻)
* [推荐库](#推荐库)
* [每周一练](#每周一练)

## 原创

- [在VS Code中调试REST API](https://juejin.im/post/6859650506155884552)：使用`Rest Client`调试接口

## 翻译

- [提升效率的15个命令行工具](https://juejin.im/post/6859121917442555918)：dev.to本周热门文章翻译

## 文章与新闻

- [WebAssembly 如何演进成为“浏览器第二编程语言”？](https://www.infoq.cn/article/4qgBeSHGipa7A9HAr7DP)：wasm的发展史
- [Flutter 动态化在最右 App 中的实践](https://www.infoq.cn/article/MIa5AN2JE51uor4JeiPG)：js控制flutter渲染
- [React Fast Refresh](https://medium.com/javascript-in-plain-english/what-is-react-fast-refresh-f3d1e8401333)：`React Hot Loader`的下一代解決方案
- [使用`Vue composition`构建数据层](https://medium.com/javascript-in-plain-english/building-a-data-layer-with-vue-and-composition-api-547cc9761b4c)：利用`Vue composition`构建一个通用的数据层，相关实现：[vue-concurrency](https://github.com/MartinMalinda/vue-concurrency)

## 推荐库

- [GraphAV](https://github.com/KarimElghamry/GraphAV)： 算法可视化
- [vue-use-infinite-scroll](https://github.com/jfet97/vue-use-infinite-scroll)：使用`Vue composition`实现无线滚动
- [Bumbag UI](https://github.com/bumbag/bumbag-ui)：一个React UI库

## 每周一练

### 获取最近插入的值

获取数据 get(key) - 如果关键字 (key) 存在于缓存中，则获取关键字的值（总是正数），否则返回 -1。

写入数据 put(key, value) - 如果关键字已经存在，则变更其数据值；如果关键字不存在，则插入该组「关键字/值」。当缓存容量达到上限时，它应该在写入新数据之前删除最久未使用的数据值，从而为新的数据值留出空间。


#### 示例：

```js
const cache = new ZYCache( 2 /* 缓存容量 */ );

cache.put(1, 1);
cache.put(2, 2);
cache.get(1);       // 返回  1
cache.put(3, 3);    // 该操作会使得关键字 2 作废
cache.get(2);       // 返回 -1 (未找到)
cache.put(4, 4);    // 该操作会使得关键字 1 作废
cache.get(1);       // 返回 -1 (未找到)
cache.get(3);       // 返回  3
cache.get(4);       // 返回  4
cache.put(3, 6);    
cache.put(3);       // 返回  6
```

#### 要求：
get、put方法都需要在 O(1) 时间复杂度内完成，空间复杂度O(n)，第一个写出来的小伙伴@陈金伙，奖励一杯星巴克 ☺

```js
/**
 * @param {number} capacity
 */
var ZYCache = function(capacity) {

};

/** 
 * @param {number} key
 * @return {number}
 */
ZYCache.prototype.get = function(key) {

};

/** 
 * @param {number} key 
 * @param {number} value
 * @return {void}
 */
ZYCache.prototype.put = function(key, value) {

};
```
