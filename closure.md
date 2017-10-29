# 闭包

### 概念



### 示例

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
