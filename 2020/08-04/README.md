# 2020年8月第4周 - 智云健康前端技术每周文摘

## 文摘目录

* [原创](#原创)
* [翻译](#翻译)
* [文章与新闻](#文章与新闻)
* [推荐库](#推荐库)
* [每周一练](#每周一练)

## 原创

- [使用 Lighthouse CI 进行前端页面性能分析(一)](https://juejin.im/post/6865908266199842824)：前端页面性能分析

## 翻译

- [6种方式秀出你的代码](https://juejin.im/post/6865870226534514695)：dev.to本周热门文章翻译

## 文章与新闻

- [Chrome 开发者工具的 11 个高级使用技巧](https://www.infoq.cn/article/wRIy35uYH7jDQ49DuGhx)
- [如何构建微前端](https://blog.bitsrc.io/how-we-build-micro-front-ends-d3eeeac0acfc)
- [WebAssembly 是 Deno 的好搭档](https://www.infoq.cn/article/bkXMMfMruVPC8MjAODIR)

## 推荐库

- [jstime](https://github.com/jstime/jstime)： Rust编写的js运行时
- [umami](https://github.com/mikecao/umami)：开源的网站分析工具
- [embla-carousel](https://github.com/davidcetinkaya/embla-carousel)：一个超流畅的React滚动组件

## 每周一练

### 苹果面试题

提供以下两个链表：

`4 -> 5 -> 7 -> 8` 与 `3 -> 5 -> 8`，每一个链表代表一个相反顺序的数字，因此：

`4 -> 5 -> 7 -> 8`代表：8754

`3 -> 5 -> 8`代表：853

请编写一个方法来将两个数字相加并将其作为另一个链表返回？

```javascript
// list1: 4 -> 5 -> 7 -> 8
// list2: 3 -> 5 -> 8

addLLNums(list1, list2);

// 应该返回：7 -> 1 -> 6 -> 9
// 8764 + 853 = 9617
```

```javascript
// Available Data Structures
function Node(val) {
  this.val = val;
  this.next = null;
}

function LinkedListNode(val) {
  this.val = val;
  this.next = null;
}

var list1 = new LinkedListNode(3);
var nodes1 = [4, 5, 6, 7, 8, 9, 10];
createNodes(list1, nodes1);

var list2 = new LinkedListNode(1);
var nodes2 = [2, 3, 4, 5, 6, 7, 8];
createNodes(list2, nodes2);

function createNodes(head, nodes) {
  for (let i = 0; i < nodes.length; i++) {
    var newNode = new LinkedListNode(nodes[i]);
    head.next = new newNode;
    head = newNode;
  }
}

/*
 * @param {LinkedListNode} list1
 * @param {LinkedListNode} list2
 * @return {LinkedListNode}
 */

function addLLNums(list1, list2) {
  // add list1 and list2
  return result;
}
```

