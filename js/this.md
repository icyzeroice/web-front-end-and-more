# this

`this` 指向调用函数的对象。在非严格模式下，直接调用函数时（而非通过对象调用方法），`this` 会被解释为全局对象 `window`，而在严格模式（`'use strict;'`）下，`this` 会因为没有对象去指向而被解释为 `undefined`。

### 参考

- [《JavaScript 权威指南（第6版）》 - 5.7.3 "use strict"](#)