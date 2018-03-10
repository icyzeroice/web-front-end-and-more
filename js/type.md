# 类型

### 动态类型转换

```js

+'' // 0
-'' // -0
-+0 // -0
+-0 // -0

1 + '' // "1"
1 + +'' // 1

1 + '2' // "12"
1 + +'2' // 3

12 + '0' - 1 // 119

+'c' // NaN
1 + 'c' // "1c"
-'c' // NaN
1 - 'c' // NaN
typeof NaN // "number"

```

### 基本类型

##### null

##### undefined

##### number

##### string

##### object

```js
null == undefined // true
null === undefined // false
null == 0 // false // 注意这里 null == 0 是 false，在 C 语言里 NULL == 0 是 true
null === 0 // false
true == 1 // true // 这里同 C 语言
true === 1 // false
false == 0 // true // 这里同 C 语言
false === 0 // false
```

### 内置类型

##### Boolean

##### Number

##### String

##### Array

##### Object

##### Date

### Reference

https://segmentfault.com/q/1010000007552319