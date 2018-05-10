# 前端跨域解决方案

### \<iframe\>

### JSONP

**JSONP** 不是一种协议，只是大家约定俗成的一种实现跨域的写法（有人称之“伪协议”）。它使用 **浏览器允许 `src` 属性使用 **HTTP GET** 方式请求非同源地址**的特性，将同源 JS 脚本中接受、处理后端数据的 **方法名** （回调函数）放进 **URL** 的查询串（query）中，后端在接收到此请求后分析查询串中的回调函数名，将 **后端数据** 以字符串拼接的方式放进这个回调函数中，作为响应的实体返回给浏览器。这样浏览器收到响应，会将响应的正文当做 JS 代码执行，这样这个回调函数便将后端数据当做函数实参传入，作进一步操作。

```js
/* https://www.a.com/index 前端 */
<script>
  function funcName(data) {
      
    /* 处理 data 数据... */
    
    return data && data.iWanna;
  }
</script>

<script src="https://www.b.com/api?other=info&callback=funcName#hash">
```

```js
/* https://www.b.com/api 后端 */
const querystring = require('querystring');
const http = require('http');

const server = http.createServer((req, res) => {

  let data = {
    name: 'Ice Zero',
    iWanna: 'Good Offers'
  };
  
  // req.url 得到 `/api?other=info&callback=funcName`
  let funcName = querystring.parse(req.url.split('?')[1]).callback;

  // 字符串拼接，将数据放入前端回调函数中
  res.write(`${funcName}(${JSON.stringify(data)})`);
  res.end();
  
}).listen(80);
```

> JSONP 缺点：
>  * 只支持 HTTP GET 请求方式
>  * 数据全部放在 URL 上，想给后端传递数据时较为麻烦，且有限
>  * 有安全风险，可能会形成 XSS 漏洞


### CORS


### window.name

### window.postMessage()



### 参考

- [常见跨域解决方案](https://www.cnblogs.com/roam/p/7520433.html)
