# 2020年9月第2周 - 智云健康前端技术每周文摘

## 文摘目录

- [翻译](#翻译)
- [文章与新闻](#文章与新闻)
- [推荐库](#推荐库)
- [每周一练](#每周一练)

## 翻译

- [设计一个 JS 插件系统](https://juejin.im/post/6871077497044205575)

## 文章与新闻

- [零日攻击：在图片中隐藏你的js代码](https://dev.to/sebastianstamm/this-image-is-also-a-valid-javascript-file-5fol)
- [深入了解JS引擎：V8](https://dev.to/edisonpappi/how-javascript-engines-chrome-v8-works-50if)
- [如何学习任何算法与数据结构](https://dev.to/codinglanguages/how-to-learn-not-memorize-any-algorithm-or-data-structure-analysis-of-20-problem-solving-techniques-you-must-know-d77)

## 推荐库

- [Chromogen](https://github.com/oslabs-beta/Chromogen)：生成[Recoil](https://recoiljs.org/)测试文件
- [remember](https://github.com/manikandanraji/remember)： 一个web端笔记应用，同时[支持chrome扩展使用](https://github.com/ravisojitra/notebook)
- [fastest-levenshtein](https://github.com/ka-weihe/fastest-levenshtein)：测量字符串之间的差异
- [vscode-debug-visualizer](https://github.com/hediet/vscode-debug-visualizer)：vscode可视化调试插件

## 每周一练

实现类似解构赋值的算法，具体例子如下所示：

```text
 输入：[1, [2, 3, [4]], 5]  '[a, [b, [c], e], d, f]'
 输出：{ a: 1, b: 2, c: 4, e: undefined, d: 5, f: undefined }
 注意：e和f没有匹配到任何值
```
```js
/**
 * @param {Array} a
 * @param {String} b
 */
 function dismantleArray(a, b) {}
```

期望结果:

```js
const res = dismantleArray([1, [2, 3, [4]], 5], '[a, [b, [c], e], d, f]')
console.log(res) // { a: 1, b: 2, c: 4, e: undefined, d: 5, f:undefined }
```
