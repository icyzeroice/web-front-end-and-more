# 闭包（Closure）

### 概念

闭包，即构建一个封闭的作用域，使其内部的变量不会影响其外部的（污染作用域）。同时可根据实际需求，可以将内部变量通过 `return` 或者挂载在内部作用域可以访问的外部变量上，将内部变量暴露到外部作用域中。

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


### 示例 2

```js
var array = [];
function demo() {
  
}
```