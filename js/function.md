# 常用函数

### JSON

```js
let target = {
  name: 'ice'
};

JSON.stringify(target); // '{"name":"ice"}'
JSON.toString(target); // '[object JSON]'
JSON.valueOf(target); // JSON {Symbol(Symbol.toStringTag): "JSON", parse: function, stringify: function}
JSON.toLocaleString(target); // '[object JSON]'


```

### call & apply & bind

```js
function demo() {
  this.print = function (arg1, arg2, arg3) {
    console.log(this, arg1, arg2, arg3);
  }
}
let d = new demo();
let o = "context";

d.print(1, 2, 3); // demo{} 1 2 3
d.print.call(this, 1, 2, 3); // Window{} 1 2 3
d.print.call(o, 1, 2, 3); // String{} 1 2 3
d.print.apply(this, [1, 2, 3]); // Window{} 1 2 3
d.print.apply(o, [1, 2, 3]); // String{} 1 2 3

// `call` 和 数组的扩展运算符 `...` 结合即可取代 `apply`
d.print.call(this, ...[1, 2, 3]); // Window{} 1 2 3

// `bind` 重新构造了一个上下文改变的新方法
let newD = d.print.bind(this);
newD(1, 2, 3); // Window{} 1 2 3

// 使用 `bind` 进行函数的柯里化
let newF = d.print.bind(this, 1);
newF(2, 3); // Window{} 1 2 3
```

由实例我们可以看出，`call` 和 `apply` 都是为了改变方法运行时的上下文（context）而存在的，唯一的区别是 `call` 直接把参数序列传给方法，而 `apply` 把参数包在数组里传给方法。
而 `bind` 并非运行时改变方法指向，而是 **重新构造** 了一个函数，改变了其定义时的上下文。

推荐阅读：[call & apply & bind](https://www.cnblogs.com/coco1s/p/4833199.html)

### delete

推荐阅读： [deep-in-delete](http://bubkoo.com/2014/01/23/deep-in-delete/)

记住，delete 只删除了属性本身，而并不能同时删除（引用类型中）属性指向的对象
