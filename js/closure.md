# 闭包（Closure）

### 概念

闭包，是无论用何种手段将内部函数传递到所在的词法作用域外，它都会有对原始定义作用域的引用。这种有权访问另一个函数作用域内变量的函数都是闭包。

### 示例 1

```js
(function (window) {
  ver i = 0;
  function add() {
    i++;
  }
  window.add = add;

  // 环境为浏览器: window = window
  // 环境为 Node: window = global
})(typeof window ? window : global);

// 这样以后每调用一次 add()，都会使闭包作用域内的 i 加一
add(); // i = 1
add(); // i = 2
```
