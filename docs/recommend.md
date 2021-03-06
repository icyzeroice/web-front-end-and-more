# 前端推荐资源

> 以下是我这个初学者的个人推荐，不定时更新。虽然很多我也没读或是读过又忘了 ::>\_<::，不过先记下共勉！如果有什么不适合的地方或者推荐，欢迎各位与我交流！


### 快速入门

> 首先，入门要有一个概念：
> html 主要是写页面结构的，比如说在页面上创建一些方块；
> css 主要是写样式的，比如说我把这个方块涂成什么颜色，放在页面中的哪个位置；
> js 主要是写逻辑的，比如说这个方块你点击后会发生什么事......

##### HTML

- [HTML 入门教程](http://www.runoob.com/html/html-tutorial.html)

##### CSS

- [CSS 入门教程](http://www.runoob.com/css/css-tutorial.html)

##### JavaScript

- [JavaScript 入门教程](http://www.runoob.com/js/js-tutorial.html)

- [JQuery 入门教程](http://www.runoob.com/jquery/jquery-tutorial.html)（现在已经不推荐使用 jQuery 了，可以不学，但是建议有时间一定要看看 jQuery 的封装技巧）

- [《JavaScript 高级程序设计》](https://book.douban.com/subject/10546125/)（红宝书）[PDF](http://note.youdao.com/noteshare?id=7ce6a29ea631d4ec477c64ba1b0ddcbe)

- [《JavaScript 权威指南》](https://book.douban.com/subject/10549733/)（犀牛书）[PDF](http://note.youdao.com/noteshare?id=4a0fe0dd3a60161f9f2da8edbe00c4df)


HTML 和 CSS 迅速过一遍，主要先理解概念和他们的在前端的作用，记一下常用的标签和属性等等，重点关注下盒子模型、BFC、几种常见的布局方式等概念。

然后上面这两本书先选一本看就行了（这两本书当前最新版本主要讲 ES5 语法，更贴近 JS 语言本质，建议优先学习，尤其原型链、作用域链、this 的作用、几种常见的继承方式等概念，面试常问）

接着就需要一些实战练习，在练习中翻看 HTML 和 CSS 手册积累这些标签、属性和实践经验。重点先放在学习 JavaScript 这门语言上，然后弄清 **浏览器对象模型** (BOM $$\supset$$ DOM)。然后 HTTP 协议、前端安全也都属于基础中的基础，一定要知道。后面再去学习、深入 React / Vue 中的一个框架，弄懂原理。

##### 手册

- [MDN](https://developer.mozilla.org/zh-CN/)(合并了微软 MDSN Web、W3C 等文档，日常手册首选)

- [Can I use ...](https://caniuse.com/#home)（查看浏览器 **特性** 必备的网站）

- [W3C](https://www.w3.org)(可以看新闻，逃 ...)

- [CSS TRICKS](https://css-tricks.com/almanac/)

##### 代码风格参考

> 规范和风格一致的代码很重要！选一个你喜欢的参考就好。

- [Google - HTML/JavaScript](https://iischajn.github.io/trans/htmlcss-guide/#HTML_Formatting_Rules)
- [Airbnb - CSS](https://github.com/airbnb/css)
- [Airbnb - JavaScript](https://github.com/airbnb/javascript)
- [Baidu - Style Guide](https://github.com/fex-team/styleguide)

### 进阶推荐

- [npm-official](https://docs.npmjs.com/getting-started/what-is-npm)

- [npm-中文教程](https://www.runoob.com/nodejs/nodejs-npm.html)

##### 优先

- [《JavaScript DOM 编程艺术》](https://book.douban.com/subject/6038371/)

- [《ECMAScript6 标准入门》](http://es6.ruanyifeng.com)


##### 基础算法

- [《学习JavaScript数据结构与算法》](https://book.douban.com/subject/27129352/)

##### 设计模式

- [《JavaScript 设计模式》](https://book.douban.com/subject/26589719/)

- [《JavaScript 设计模式与开发实践》](https://book.douban.com/subject/26382780/)

##### 知识体系

- [《现代前端技术揭秘》](https://book.douban.com/subject/27021790/)


### 现代前端框架

##### MV* 框架

- [Angular](https://angular.io)

- [React](https://reactjs.org/)
  - 状态管理机制较弱，一般配合 [React Router]() 和 [Redux]()
  - 开箱即用 [create-react-app](https://github.com/facebookincubator/create-react-app)
  - 想深入 React 但不知道从何下手，可以先看看这本书：[《深入 React 技术栈》](https://book.douban.com/subject/26918038/)

- [Vue](https://cn.vuejs.org/index.html) 
  - 同上配合 [Vue Router]() 和 [Vuex]()
  - 开箱即用 [vue-cli](https://github.com/vuejs/vue-cli)

- [Aurelia](http://aurelia.io/)


##### UI 库

- [Ant Design](https://ant.design/index-cn)

- [Element](http://element-cn.eleme.io/#/zh-CN)

- [Materialize](http://materializecss.com/)

- [Bootstrap](https://v4.bootcss.com/)


##### 开发移动应用或桌面应用

- [Cordova](https://cordova.apache.org/)

- [React Native](https://facebook.github.io/react-native/) --- MNV* 型框架

- [ionic](https://ionicframework.com/)

- [Node-Webkit](https://nwjs.io/)

- [Electron](https://electronjs.org/)


##### 其他

- [Polymer](https://www.polymer-project.org/) --- 一种 Web Components 实现的 Polyfill

- [TypeScript](https://www.tslang.cn/) --- JavaScript 的强类型解决方案，微软出品，必属精品系列

- [BuckleScript](https://bucklescript.github,io) --- 一种更安全的 JavaScript 编译器

- JavaScript 真是一门罪恶的语言，[证据在此](https://github.com/jashkenas/coffeescript/wiki/List-of-languages-that-compile-to-JS)


### Node.js

- [Node.js 官方文档](https://nodejs.org/dist/latest-v8.x/docs/api/)

- [Node.js 中文文档](http://nodejs.cn/api/)

- [《Node.js 深入浅出》](https://book.douban.com/subject/25768396/)

如果觉得官方文档有点乱，不知道 Node.js 的应用从何下手，可以看看这本全是小 Demo 的书，跟着练习：

- [《Node.js 硬实战 - 115个核心技巧》](https://book.douban.com/subject/26937390/)


### Web 前端安全

- 面试主要搞懂 XSS 和 CSRF

- [《Web 前端黑客技术揭秘》](https://book.douban.com/subject/20451827/)

- [《白帽子讲 Web 安全》](https://book.douban.com/subject/25910557/)


### Web 图形

- [《HTML5 Canvas 核心技术》](https://book.douban.com/subject/24533314/)

- [《WebGL 编程指南》](https://book.douban.com/subject/25909351/)


| 图像处理库 | |
|:--:|:--:|
| [CamanJs](http://camanjs.com/) | |
| [glfx.js](http://evanw.github.io/glfx.js/) | 不再维护 |
| [AlloyPhoto](http://alloyteam.github.io/AlloyPhoto/) | 不再维护 |

| 2D、3D、VR、AR 库推荐 | |
|:--:|:--:|
| [three](https://threejs.org/) | |
| [pixijs](http://www.pixijs.com/) | |
| [AR.js](https://github.com/jeromeetienne/AR.js) | |
| [Aframe](https://github.com/aframevr/aframe) | Mozilla 社区出品，必属精品 |
| [react-vr](https://github.com/facebook/react-vr) | |


### Web AI 库

|  | |
|:--:|:--:|
| [tracking.js](https://trackingjs.com/) | |
| [regl-cnn](https://erkaman.github.io/regl-cnn/src/demo.html) | |
| [deeplearn.js](https://deeplearnjs.org/) | |
| [Synaptic](http://caza.la/synaptic/#/) | |
| [ml.js](https://github.com/mljs/ml) | |
| [natural](https://github.com/NaturalNode/natural) | |
| [brain.js](https://github.com/harthur/brain) | 不再维护 |
| [convnet.js](https://github.com/karpathy/convnetjs) | 不再维护 |

### 前端数据可视化

|  |  |
|:--:|:--:|
| [Echarts](http://echarts.baidu.com/) | 百度出品 |
| [D3](https://www.google.com.hk/search?q=d3) | |
| [Antv](https://antv.alipay.com/index.html) | 阿里出牌 |
| [Processing.js](http://processingjs.org/) | Processing 的 JavaScript 实现 |


### 溯源推荐

- [《HTML5 权威指南》](https://book.douban.com/subject/25786074/)

- [《CSS 权威指南》](https://book.douban.com/subject/2308234/)

- [《你不知道的 JavaScript（上卷）》](https://book.douban.com/subject/26351021/)

- [《你不知道的 JavaScript（中卷）》](https://book.douban.com/subject/26854244/)

- [《你不知道的 JavaScript（下卷）》](https://book.douban.com/subject/27620408/)

- [《HTTP 权威指南》](https://book.douban.com/subject/10746113/)

- [《计算机网络：自顶向下方法》](https://book.douban.com/subject/26176870/)

- [《Webkit 技术内幕》](https://book.douban.com/subject/25910556/)（这本书里有讲页面渲染、浏览器缓存机制、js 引擎机制等等内容，强推）


### 前端知识图谱个人总结

- [前端知识图谱](./knowledge-graph.md)

### 其它

- [前端导航 - 腾讯](http://www.alloyteam.com/nav/)