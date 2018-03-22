# JavaScript 学习笔记 —— 原型链

> **[warning] For warning**
>
> 未完成，下面为胡言乱语：

首先，我们要明确 [JavaScript 中的类型系统](./type.md)，我们知道 `typeof` 会区分出 `"object"` 和 `"function"` 这两种类型，其实

`prototype` 属性引用的其实是一个 **原型对象**，这个原型对象是在构造函数中自动生成的一个对象

而 `__proto__` 其实是一个对这个对象 **原型** 的引用，它指向它所继承的对象

**构造函数** 是一种用来初始化新建对象的函数。

### new 操作符

### 参考

- [MDN - 继承与原型链](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)