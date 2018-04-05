# JavaScript 学习笔记 —— this

`this` 指向调用函数的对象。也就是说我们在没有手动绑定（`bind()`、箭头函数）时，`this` 的指向是不决定的，是在运行过程中可以动态变化的。这和 `Java` 的 `this` 在编译期间就绑定确定不同。

### 函数中的 this

我们知道函数有两种形式：

##### 1. 函数

一种是直接声明的独立函数单元，在非严格模式下，直接调用函数时（而非通过对象调用方法），`this` 会被解释为全局对象 `window`，而在严格模式（`'use strict'`）下，`this` 因为没有对象去指向而被解释为 `undefined`[^1]。

```js
function cons() {
  this.a = 1;
  this.b = function () {
    console.log('2');
  };
}

// 所以在非严格模式下，直接调用这样的函数
// 是会给全局对象 `window` 绑定上 `a`、 `b` 两个全局变量的。
cons();
console.log(a); // 1
b();            // 2

function strictCons() {
  'use strict';
  
  this.a = 1;
  this.b = function () {
    console.log('2');
  };
}

// 而严格模式下，直接调用的函数里的 `this` 为 `undefined`，
// 无法进行 . 操作访问，所以会直接抛出 `TypeError`。
strictCons();
```

##### 2. 对象方法

另一种是挂载在对象属性上的方法。这时，对象调用方法时，即访问对象这个属性构成了一个 **属性访问表达式**，`this` 便会指向调用此方法的对象。对于直接使用 `var` 或者 `function` 声明的全局函数，是会直接绑定在 `window` 上的，我们可以使用上面的方式直接调用函数，这样 `this` 为 `undefined`；但是我们也可以通过 `window` 这个全局对象来调用这个方法，这样 `this` 便可以指向调用它的对象 `window`。同理可以延伸到其他对象和其方法间的关系。（当然，这个全局的规则不适用于 `let` 或 `const` 声明的函数，因为它们生成的是[块级作用域](./scope.md#块级作用域)，不会绑定在 `window` 上。）

注意嵌套函数的直接调用属于第一种形式，所以在嵌套函数中 `this` 的指向一定要注意，可以声明一个变量去缓存它，以便在嵌套函数中访问上级函数作用域的 `this`。

```js
let a = {
  b: function () {
    let _this = this;     // 变量替代，引用这个作用域下指向对象 `a` 的 `this`
    console.log(this);    // a {}

    c();                  // 直接调用函数，并没有对象调用它哦

    function c() {
      console.log(this);  // 非严格模式下输出 `window`，严格模式下输出 `undefined`
      console.log(_this); // a {}
    }
  }
}
a.b();
```



### apply & call & bind



### 参考

[^1]: 《JavaScript权威指南（第6版）》5.7.3节 "use strict"
[^2]: https://www.ibm.com/developerworks/cn/web/1207_wangqf_jsthis/index.html "深入浅出 JavaScript 中的 this"