# JavaScript 函数式编程技巧

### Curry

柯里化是函数式编程中很重要的一个技巧，

##### 柯里化

柯里化，是指将多个参数分解成少量参数的技巧。

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

> 曾遇到过一个面试题，大概是这样的，已知一个函数 `function func(a, b, c, d) {}` 写一个函数 `curry`，可以做到 `var createFunc = curry(func)`，然后 `createFunc(a)(b)(c)(d)`。

我这里用递归写了个简陋的……

```js
// TODO: what if the number of parameters is unstable?
function normal2curry(callback) {

  let argsArray = [];
  let funcLen = callback.length;

  return function circle(...rest) {
    
    argsArray = argsArray.concat(rest);

    if (argsArray.length === funcLen) {
      callback(...argsArray);
    } else {
      return circle;
    }

  }
}

function test1(a, b, c, d) {
  console.log(a, b , c, d);
  console.log(a + b + c + d);
}

let test2 = normal2curry(test1);
test1(1, 2, 3, 4);
test2(1)(2)(3)(4);
```

##### 反柯里化
