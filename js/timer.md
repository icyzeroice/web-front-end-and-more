# 计时器

### setTimeout

```js
(function a() {
  
  console.time('exec');
  console.time('timer0ms');
  setTimeout(function () {
    console.timeEnd('timer0ms');
    console.log(1);
  }, 0);

  console.time('timer1ms');
  setTimeout(function () {
    console.timeEnd('timer1ms');
    console.log(2);
  }, 1);

  console.time('timer1000ms');
  setTimeout(function () {
    console.timeEnd('timer1000ms');
    console.log(1000);
  }, 1000);

  console.log(3);
  console.log(4);

  var count = 100;
  while(count--) {
    console.log(5);
  }
  console.timeEnd('exec');

})();

// 3
// 4
// (100)5
// exec: 5.159912109375ms
// timer0ms: 5.40380859375ms
// 1
// timer1ms: 5.534912109375ms
// 2
// timer1000ms: 1000.4521484375ms
// 1000
```

从这个例子中我们发现 JS 的计时器函数 `setTimeout` 并不按照我们规定的时间执行，这是为什么呢？

我们都知道，JS 引擎线程是单线程的，我们使用 `setTimeout` 时，回调函数会先将其放在事件队列中进行计数，然而计数完成后并不会立即执行，而是等待 JS 线程空闲下来时再执行。

也就是说，计时完成时，若 JS 引擎线程是空闲的，那么回调函数便会立刻执行，但如果此时 JS 引擎并非空闲，而是像示例里面这样，5ms 内都在执行语句中，那么便阻塞了计时器事件回调函数的执行，只有在 5ms 后，常规语句执行完成，JS 引擎线程空闲下来了，我们才能执行计时完成的计时器事件。所以本该立刻执行、延缓 1ms 执行的回调函数居然被阻塞了，直到 5ms 后才能执行到。而 1000ms 时，JS 线程很闲，就没有造成什么影响了。

```js
console.time('timerWhile');
setTimeout(() => {
  console.timeEnd('timerWhile');
  let count = 1000;
  while(count--) {
    console.log(1);
  }
}, 1000);

console.time('timerNormal');
setTimeout(() => {
  console.timeEnd('timerNormal');
  console.log(2);
}, 1000);

// timerWhile: 1000.468994140625ms
// (1000) 1
// timerNormal: 1050.19091796875ms
// 2
```

所以，我相信你现在一定能清楚地说明为什么上面这个 `2` 不是经过 1000ms 打印出来，而是经过 `1050ms` 才打印出来了！

### setInterval

