# 前端工程化自动化工具


### Webpack

简单示例请见：https://github.com/icyzeroice/webpack-demo

首先要说明的一点是，webpack 不是一个完整的前端构建工具，这一点 webpack 官网一开始就有说明：

> At its core, webpack is a module bundler for modern JavaScript applications. When webpack processes your application, it recursively builds a dependency graph that includes every module your application needs, then packages all of those modules into one or more bundles.

我们可以看到，webpack 是一个模块打包的解决方案，可以解决模块化开发过程中的各种依赖关系，而且 webpack 可以将所有资源和代码文本都看成模块，进行统一处理，如图：

![webpack module bundler](./img/webpack.png)

webpack 工作时首先会分析入口文件（entry）及其依赖和依赖的依赖（请自行闹补递归），明确依赖关系后进行打包工作，输出一个或多个打包文件（output），所以非模块化开发的项目各种资源和文件没有明确依赖关系，用 webpack 是没有效果的。

### Gulp



简单示例请见：https://github.com/icyzeroice/gulp-demo

### 其他 (暂时仅作列举，未实际使用过)

##### Grunt

##### Browserify