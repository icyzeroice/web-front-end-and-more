# 常用编程范式

### 结构化程序

### 函数式编程

##### 柯里化

柯里化（Curry），是指将多个参数分解成多个函数，每个函数只传入一个参数的技巧。

```js
// 原函数
let add = (x, y, z) => x + y + z

// 柯里化
function curry(x) {
  return function (y) {
    return function (z) {
      return add(x, y, z)
    }
  }
}

// usage demo 1
var curry1 = curry(1);
var curry2 = curry1(2);
var curry3 = curry2(3);
console.log(curry3); // 6

// usage demo 2
console.log(curry(1)(2)(3)); // 6

```

融合 ES6 的箭头函数，可以写成这样：
```js
let curry = x => y => z => console.log(add(x, y, z))

curry(1)(2)(3) // 6
```
是不是顿时觉得神清气爽？

曾经遇到过一道题目，大概是这样的：[传送门](../others/interview.md#题目二（函数式编程）)

##### 反柯里化

> 占位

##### 偏函数

偏函数是指固定某个函数中的某些参数，返回新的函数的技巧，注意和柯里化区分开。

```javascript
function partial(x) {
  return (y, z) => add(x, y, z)
}

let partialAdd = partial(1)
partialAdd(2, 3) // 6
```




### 面向对象程序设计

### 响应式编程

Reactive Programing
