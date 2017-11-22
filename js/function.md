# 常用易混淆函数

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

### call & apply

```js
function demo1(arg1, arg2, arg3) {
  
}
```