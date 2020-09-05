# 2020年9月第1周 - 智云健康前端技术每周文摘

## 文摘目录

* [原创](#原创)
* [文章与新闻](#文章与新闻)
* [推荐库](#推荐库)
* [每周一练](#每周一练)

## 原创

- [神秘的JS字符串隐写术](https://juejin.im/post/6867319399947681806)：利用Unicode隐藏字符加密你的可见字符

## 文章与新闻

- [你应该了解的 5 种 TypeScript 设计模式](https://www.infoq.cn/article/2VJ1tSD1dimElT3qg0Kv)
- [使用GetX管理Flutter的状态](https://medium.com/flutter-community/the-flutter-getx-ecosystem-state-management-881c7235511d)
- [探索 Flutter 中线程模型 / 消息循环的底层逻辑](https://www.infoq.cn/article/MJ6lmZSLbSZPZ5L7DqqG)

## 推荐库

- [GetX](https://pub.dev/packages/get)：Flutter体系化解决方案，包含高性能的状态管理、智能依赖注入、快速的路由管理
- [neo](https://github.com/neomjs/neo)：创建多线程的Web应用
- [kvs](https://github.com/azu/kvs)：浏览器、Node、内存通用的KV存储库
- [light-date](https://github.com/xxczaki/light-date)：超轻量的日期处理库（157字节）
- [shift-ctrl-f](https://github.com/model-zoo/shift-ctrl-f)：通过自然语言处理来搜索网页上的内容
- [ztext.js](https://bennettfeely.com/ztext/)：使用ztext.js开发简单的3D网站
- [arwes](https://github.com/arwes/arwes)：一套科幻主题的UI框架

## 每周一练

### 谷歌面试题

`编辑距离`是一种量化两个字符串差异的方法，其含义是：将一个字符串转换为另一个字符串的最小转换次数来计算的。转换包括`插入`、`删除`和`替换`。

比如 cat 与 cat，编辑距离为0。

举个例子：

```javascript
getEditDistance('mitten', 'sitting'); // 3
```

原理：

```text
1. mitten -> sitten （用's'替换'm'）
2. sitten -> sittin （用'i'替换'e'）
3. sittin -> sitting （在末尾插入'g'）
```

你能写一个`getEditDistance(a, b)`方法来返回编辑距离吗？

```javascript
// Available Data Structures
class Graph {
  constructor() {
    this.adjacencyList = new Map();
    this.verticesCount = 0;
  }

  addVertex(nodeVal) {
    this.adjacencyList.set(nodeVal, []);
    this.verticesCount++;
  }

  addEdge(src, dest) {
    this.adjacencyList.get(src).push(dest);
    this.adjacencyList.get(dest).push(src);
  }

  removeVertex(val) {
    if (this.adjacencyList.get(val)) {
      this.adjacencyList.delete(val);
    }
    
    this.adjacencyList.forEach((vertex) => {
      const neighborIdx = vertex.indexOf(val);
      if (neighborIdx >= 0) {
        vertex.splice(neighborIdx, 1);
      }
    })
  }

  removeEdge(src, dest) {
    const srcDestIdx = this.adjacencyList.get(src).indexOf(dest);
    this.adjacencyList.get(src).splice(srcDestIdx, 1);
  
    const destSrcIdx = this.adjacencyList.get(dest).indexOf(src);
    this.adjacencyList.get(dest).splice(destSrcIdx, 1);
  }

  printNeighbors() {
    const result = [];
    
    for (let vertex of this.adjacencyList.keys()) {
      const neighbors = [];
      neighbors.push(`${vertex}:`);
      this.adjacencyList.get(vertex).forEach((neighbor) => {
        neighbors.push(neighbor);
      });
      result.push(neighbors.join(" "));
    }

    return result;
  }

  verticesCount() {
    return this.verticesCount;
  }

  reverse() {
    const graph = new Graph();
    for (let [src, dests] of this.adjacencyList) {
      graph.addVertex(src);
    }

    for(let [src, dests] of this.adjacencyList) {
      for (let dest of this.adjacencyList.get(src)) {
        graph.adjacencyList.get(src).push(dest);
      }
    }

    return graph;
  }
}

var matrix1 = [
  [1, 1, 0, 0, 0],
  [0, 1, 1, 0, 0],
  [0, 1, 0, 1, 0],
  [1, 0, 0, 0, 0]
];

var matrix2 = [
  [1, 1, 0, 0],
  [0, 0, 1, 0],
  [0, 1, 1, 0],
  [1, 0, 0, 0]
];

var planeMatrix1 = [
  [".", ".", ".", "P"],
  [".", ".", ".", "P"],
  ["P", "P", ".", "P"],
  [".", ".", ".", "P"],
];
```



