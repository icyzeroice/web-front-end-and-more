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

##### 我的解答

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