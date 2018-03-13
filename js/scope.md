# 作用域


### 提升

```js

a(); // 3

function a() {
    console.log(1);
}

var a = function () {
    console.log(2);
}

a(); // 2

function a() {
    console.log(3);
}

a(); // 2

```