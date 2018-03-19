# 兼容性

### document.getElementById()

1. 在 IE7 及之前是不区分大小写的，如 `document.getElementById('mydiv')` 是可能获取到 `id="myDiv"` 的元素！

2. 我们知道如果页面中有多个元素 `id` 值相同，那么 `document.getElementById()` 就只会返回文档中第一个为此 `id` 的元素。然而在 IE7 及之前，对应表单元素（如 `<button>`、`textarea`、`<select>`），如果有 `name` 属性，`document.getElementById('mydiv')` 获取第一个 `name` 或 `id` 值为不区分大小写的 `mydiv`。也就是说，在前表单元素 `name` 同值可能会屏蔽真正想获取的 `id` 值为此的元素。
