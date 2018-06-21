# JavaScript Tricks

### 逗号运算符

作用：依次执行表达式，并返回最后一个表达式的值。

* Example 1

```js
(1, 9) // 9


function do1() { /* Coding Here */ }
function do2() { /* Coding Here */ }
function do3() { /* Coding Here */ }

function miniLine() {
  return (do1(), do2(), do3())
} // return the value of function do3
```

* Example 2

```
var a = {
  b: function () {
    console.log(this)
  },
  c: function () {}
}

a.b(); // { b: f, c: f }，注意这里要加分号，因为下一行的左括号不会触发自动添加括号的机制（ASI）

(a.b)(); // 同上，这里前一组括号的作用是分组，后一组括号作用是调用

(0, a.b)() // Window {}，这里逗号运算返回了 a.b 的方法为函数，从而使 b 不再作为对象方法调用
```
