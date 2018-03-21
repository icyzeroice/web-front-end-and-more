# 面试题？

### 题目一（DOM 操作）

> 实现一个方法genCssSelector，可以根据一个给定的元素生成一个CSS选择器，通过这个选择器可以快速定位到这个元素（document.querySelector(A)）

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <div id="page">
        <div class="content main">
            <div class="refer">
                <ul>
                    <li></li>
                    <li></li>
                </ul>
            </div>
        </div>
    </div>
    <script>
        var genCssSelector = function(){

            // your code here

        }

        document.addEventListener('click', function(e){

            //点击li时，返回：html body #page .content.main .refer ul li
            console.log(genCssSelector(e.target));
        });
    </script>
</body>

</html>
```

这是要考 sizzle 引擎吗？反正我是这么想的：

```js
var cssSelectorStr, tempNode = [];

for (var curNode = arguments[0]; curNode !== document; curNode = curNode.parentNode) {

    if (curNode.id !== '') {
        tempNode.unshift('#' + curNode.id);
    } else if (curNode.className !== '') {
        tempNode.unshift('.' + curNode.className.replace(/\s/g, '.'));
    } else {
        tempNode.unshift(curNode.tagName.toLowerCase());
    }

}

tempNode = tempNode.toString().replace(/\,/g, ' ');

return tempNode;
```

### 题目二（函数式编程）

> 曾遇到过一个面试题，大概是这样的，已知一个函数 `function func(a, b, c, d) {}` 写一个函数 `curry`，可以做到 `var createFunc = curry(func)`，然后以 `createFunc(a)(b)(c)(d)` 形式调用。

我这里用递归写了个简陋的……不知道有没有更好的方法……



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