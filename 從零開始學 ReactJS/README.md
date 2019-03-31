[從零開始學 ReactJS](https://kdchang.gitbooks.io/react101/content/)

# Ch01 前端工程簡介和 React 生態系簡介

## [Web 前端工程入門簡介](https://github.com/kdchang/reactjs101/blob/master/Ch01/front-end-introduction.md)

HTML、CSS、JavaScript 是前端工程最重要的技能基础，当前的 WEB 平台已不再局限于桌面浏览器，而是需面对更多的跨平台、跨浏览器的应用开发场景：
* 网页浏览器（Web Browser）
* 通过 CLI 指令去操作的 Headless 浏览器（Headless Application）。如：[phantomJS](http://phantomjs.org)、[CasperJS](http://casperjs.org)
* 运行在 WebView 浏览器核心（WebView Application）的应用。如：[Apache Cordova](https://cordova.apache.org)、[Electron](http://electron.atom.io)等行動、桌面應用程式開發
* 原生应用程序（Native Application），通过 Web 技术撰写原生应用程式。如[React Native](https://facebook.github.io/react-native)、[Native Script](https://www.nativescript.org)

前端经历了框架百花齐放的时代，有更多好用的工具可以协助开发，但前端工程师似乎并没有变得比较轻松。React 让许多革新性的 Web 观念开始流行起来，例如：Virtual DOM、Web Component、更直觉的宣告式 UI 设计、更优雅的实现 Server Rendering 等。

## [React 生態系（Ecosystem）入門簡介](https://github.com/kdchang/reactjs101/blob/master/Ch01/react-ecosystem-introduction.md)

React 是一个专注于 UI（View）的 JavaScript 函式库。了解学习现代化 Web 开发的重要概念，如模块化、ES6+、Webpack、Babel、Eslint、函数式程式设计。

### ReactJS

ReactJS 是 JavaScript 函式库，以 MVC 框架来看，属 View 范畴。

### JSX

JSX 实际上是一种语法糖。在 JSX 中 HTML 和 组建这些元素标签的程序码（JavaScript）有着紧密的关系。也可选择不在 React 中使用 JSX 。

### NPM

NPM（Node Package Manager）是 Node.js 下的主流套件管理工具。NPM 主要基于 CommonJS 规范，通常需搭配 Browserify 才能在前端使用 NPM 的模块。然而因为 NPM 使用嵌套依赖树（Nested Dependency Tree），避免了依赖冲突，但可能会引入不同版本的组件，造成依赖文件过大。而与之不同 Bower 使用扁平化依赖树（Flat Dependency Tree），同一个包, 只会在依赖关系中出现一次. 所以可能会有潜在的依赖冲突问题。

### ES6+

ES6+ 引入了许多新的特性和功能，弥补了 JavaScript 中一些被诟病的特性。

### Babel

通过 Babel 编译器，可以将 ES6+、JSX 等程式码转换为 ES5 语法，使得所有浏览器可识别支持。添加 `.babelrc` 进行转译规则 `preset` 和引用外挂（plugin）设定。

### JavaScript 模块化开发

* CDN-Based

    传统的 `<script>` 引入方式，使用简单却在大型应用中产生许多弊端：
    * 全局作用域容易造成变量污染和冲突
    * 文件只能依照 `<script>` 引入顺序载入，不具弹性
    * 大型应用中各种资源和版本难以维护
    * 须由开发者自行判断模块和函式库间的依赖关系

* AMD

    即非同步载入模块规范（Asynchronous Module Definition），其在定义模块时就需要定义依赖的模块。AMD 常用于浏览器端，如 RequireJS。

* CommonJS

    CommonJS 是一种同步模块载入的规范。Node.js 遵守 CommonJS 规范，使用 require 进行模块同步载入并通过 exports 、module.exports 输出模块。主要实现为 Node.js 服务端的同步载入和浏览器端的 Browserify。

* CMD

    Common Module Definition，和 AMD 类似，但相对简洁，却保持了 CommonJS 的兼容性，特色为：就近依赖，延迟执行。主要实现为 Sea.js。

* UMD

    Universal Module Definition 是为了兼容 CommonJs 和 AMD 所设计的规范，使模块能跨平台执行。

* ES6 Module

    ECMAScript6标准中定义了 JavaScript 的模块化方式，使得在开发大型复杂应用程序时更为方便且易于管理，亦可取代 AMD、CommonJS 等规范，但目前仍需通过 Babel 进行转译。

### Webpack、Browserify + Gulp

现代化网页更是个网页应用程序（WebApp）。Webpack 和 Browserify + Gulp 则是 React 开发中常用的开发工具，可以进行自动化打包、转译等。

* Webpack

    * 将 Css、图片等资源打包
    * 打包前预处理（Less、CoffeeScript、JSX、ES6等）文件
    * 依照 entry 文件不同，将 .js 拆分为多个 .js 文件
    * 整合使用丰富的 Loader（Webpack 仅能处理 JavaScript 模块，其他需载入 Loader 处理）

* Browserify

    Browserify 是可在浏览器端使用输出（export）和引用（require）来管理模块

* Gulp

    Gulp 是前端任务工具自动化管理工具（Task Runner）。通过 Grunt、Gulp 可执行重复性工作，如：文件打包、uglify、Less 转为 CSS、转译 ES6 语法等工作。提升效率，也更方便管理这些任务。

* ESLint

    ESLint 是代码规范检查工具，可在 `.eslintrc` 设定检查规则。