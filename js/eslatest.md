# ES6+ 入门

### Promise

Promise 是 ES6 标准新加入的异步编程解决方案，
先来看一个简单的例子：

```js
const isSuccess = false;

let promise = new Promise((resolve, reject) => {
  console.log('do something here!');

  if (isSuccess) {
    let value = 'done';
    resolve(value);
  } else {
    let err = new Error('failed');
    reject(err.message);
  }
});

promise.then(value => {
  console.log(value);
}, err => {
  console.error(err);
});

promise.then(value => {
  console.log(value);
}).catch(err => {
  console.error(err);
});
```
这里 Promise 被实例化即刻执行，然后我们需要在后面用 then 或 catch 处理成功或失败的结果，如果没有处理，这里因为 promise 实例执行后进入失败（reject）状态，所以应该处理，不然会有警告：

> (node:14614) UnhandledPromiseRejectionWarning: Unhandled promise rejection (rejection id: 1): failed
> (node:14614) [DEP0018] DeprecationWarning: Unhandled promise rejections are deprecated. In the future, promise rejections that are not handled will terminate the Node.js process with a non-zero exit code.

[Promise A+/A 标准]()

### Generator

### async
