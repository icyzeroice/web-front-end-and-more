# XML (eXtensible Markup Language)

可扩展标记语言

### 基本格式

XML 和 HTML 皆由 SGML 演变而来，语法上很相似，但是实际却有很大不同。

| XML | HTML |
|--|--|
| 储存、传输数据 | 显示数据 |
| 元素和属性名属性值都需要自定义 | 元素和属性名属性值已知，需要按手册使用，但也可以随意自定义元素名，会默认继承父元素特性，或者使用 Custom Elements[^1] |
| 浏览器无法理解自定义标签的含义，只能显示完整的 XML 文件内容，但是可以用 CSS 或者 XSLT 来描述样式 | 因为标签有自己的含义，可被浏览器按规则渲染，有配套的 CSS 用来写具体的样式 |
| 可以用于书写配置文件，写在HTTP 响应 body 中传输数据 | 可以由浏览器解析并显示出相应结构 |


```xml
<?xml version="1.1" encoding="utf-8"?>
<!--
首先要有 xml 文档声明
version  --+> 文档
encoding --+> 文字编码格式的声明
-->
<![CDATA[

    术语 CDATA 指的是不应由 XML 解析器进行解析的文本数据（Unparsed Character Data）

    与注释的区别是：
        CDATA 仍然是 XML 文档的一部分，会被当做数据传输，仍然属于要传输数据的一部分
        而注释只是书写时给开发者看的，可以过滤掉


    附 -> 预定义实体引用，防止直接使用一些特殊符号会使解析器解析错误：

        &lt;      <    less than
        &gt;      >    greater than
        &amp;     &    ampersand
        &apos;    '    apostrophe
        &quot;    "    quotation mark

]]>
<demoRoot>
  <!--
  一定要有一个根元素，并且元素必须要使用 / 闭合
  元素
  属性
  属性值

  属性=属性值，这种不建议使用，最好是将属性写成元素，比如
  <date>2017/11/24</date>

  可以写成
  <date year="2017" month="11" day="24"></date>

  但是最好写成下面这样，方便解析和理解数据，属性最好用在添加序列、标签等方便查询的场合
  -->
  <begin itemId="1">
    <date>
      <year>2017</year>
      <month>11</month>
      <day>24</day>
    </date>
  </begin>
  <!--
  命名空间（namespace），1.0 版本规范使用 URI 作为名称
  但是 1.1 版本已经变为使用 IRI，当然不是强制性的，你也可以使用非 ASCII 编码
  但是可能会被解析器拒绝，所以一般通用使用一段 URL 作为命名空间的名称

  xmlns 声明这一块的命名空间
  x --+> 命名空间前缀
  namespaceURI --+> 命名空间唯一标识符
  -->
  <x:demo xmlns:x="namespaceURI">
    <x:title> XML </x:title>
    <x:content> PCDATA 是被解析的字符数据（Parsed Character Data），就是写在这里啦！不过要注意，XML 对大小写和空格敏感！</x:content>
  </x:demo>

  <yy:demo xmlns:yy="https://www.demo.com/demo">
    <yy:title><yy:title>
  </yy:demo>
</demoRoot>
```

### JavaScript 获取 XML DOM

其实在 JSON 火起来之前，互联网上传输的数据主要是以 XML 格式储存的，而且即便是现在，XML 格式仍然比 JSON 应用更广。现代浏览器也给 JavaScript 提供了一套解析 XML 格式的办法。

##### 通过 Ajax 获取 XML DOM

```js
var xhr, xmlDocument;

if (window.XMLHttpRequest) {
  xhr = new XMLHttpRequest();
} else {
  // for IE5, IE6
  xhr = new ActiveXObject('Microsoft.XMLHTTP');
}

xhr.open('GET', 'demo.xml', false);
xhr.end();

// response type -- XML
// 获取 XML DOM
xmlDocument = xhr.responseXML;
```

##### 通过 DOMParser 从字符串中生成 XML DOM

DOMParser 是一个用于 DOM 解析和序列化的浏览器 API

```js
let parser, xmlDocument;
const str = '<demo>' +
                '<date id="date1" class="date1">' +
                    '<year diy="valueDIY"> 2017 </year>' +
                    '<month> 11 </month>' +
                    '<day> 24 </day>' +
                '</date>' +
            '</demo>';

if (window.DOMParser) {
  try {
    parser = new DOMParser();
    xmlDocument = parser.parseFormString(str, 'text/xml');
  } catch (err) {
    throw new Error('Check XML');
  }
} else {

  // for IE
  xmlDocument = new ActiveXObject('Microsoft.XMLDOM');
  xmlDocument.async = false;
  xmlDocument.loadXML(str);
}
```

##### 使用 JavaScript DOM 节点操作的方法操作 XML DOM

```js
// xmlDocument from above

xmlDocument.getElementById('date1') === xmlDocument.getElementsByClassName('date1')[0]; // true

xmlDocument.getElementsByTagName('year')[0].innerText; // 2017
```

同时，XML DOM 也有诸如 `getAttribute`、`childNodes` 等等 HTML DOM 的方法和属性，
也有诸如 `getAttributeNS`、`CDATASection`[^2] 等 XML DOM 自己特有的方法和属性。

更多方法见：https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model


[^1]: http://w3c.github.io/webcomponents/spec/custom/ "Custom Elements"

[^2]: https://developer.mozilla.org/zh-CN/docs/Web/API/CDATASection "CDATASection"
