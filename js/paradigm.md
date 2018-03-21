# 常用编程范式

### 结构化程序

### 函数式编程

##### 柯里化

柯里化（Curry），是指将多个参数分解成少量参数的技巧。

```js
function curry(x) {
  x = x * 1;
  return function (y) {
    y = y * 2;
    return function (z) {
      z = z * 3;
      return x + y + z;
    }
  }
}

// usage demo 1
var curry1 = curry(1);
var curry2 = curry1(2);
var curry3 = curry2(3);
console.log(curry3); // 14

// usage demo 2
console.log(curry(1)(2)(3)); // 14

```

融合 ES6 的箭头函数，可以写成这样：
```js
let curry = (x, y) => (z) => (a, b) => {
  console.log(x, y, z, a, b);
}

curry(1, 2)(3)(4, 5); // 1 2 3 4 5
```
是不是顿时觉得神清气爽？

曾经遇到过一道题目，大概是这样的：[传送门](../others/interview.md#题目二（函数式编程）)

##### 反柯里化


### 面向对象程序设计

### 响应式编程

Reactive Programing
