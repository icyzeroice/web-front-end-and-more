# 柯里化（Curry）

### 柯里化

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

### 反柯里化