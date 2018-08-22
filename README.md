![](https://parg.co/U0a)

[中文版本](./) | [English Version](./README.en.md)

#
 是笔者对于日常工作中的基于 React/Vue.js 技术栈与实践的收集(\*部分模板修改自其他项目)与沉淀，dev-config/\* 与 package.json 构成了基础的脚手架，支持最新的开发流程与默认的生产环境优化。

为了方便不同级别/熟练程度的开发者使用，笔者将模板尽可能地泛化为多个项目，包含了从入门级到生产环境等多个不同层次/复杂度的模板项目。其中，模板特性可能包括或不限于以下：

* 技术栈支持：使用 ES6/ES7 语法、允许使用 CSS Modules、SCSS、Less 并且使用 PostCSS 进行自动 Polyfill、支持使用 styled-component 进行 CSS-in-JS 样式控制、使用 Flow 作为静态类型检测工具、使用 Jest 作为默认的测试框架；

* 开发环境：使用 WebpackDevServer 部署开发服务器、支持组件热加载、使用 Babel 进行代码转换、使用 ESLint 进行代码检测、使用 DllPlugin 作为开发环境下公共代码提取工具以优化编译速度；

* 生产环境：使用 CommonChunksPlugin\*(Webpack 4 中提供了 optimization 选项) 作为生产环境下公共代码提取工具、使用 Prepack & prepack-webpack-plugin 进行代码优化、使用 offline-plugin 添加简单的 PWA 特性增强；

* 部署方式：支持独立部署（HashRouter）、支持服务端部署、支持服务端渲染；

# TOC | 目录索引

* [bundler](./bundler): 基本的构建工具使用

  * [webpack](./builder/webpack)
  * [parcel](./builder/parcel)
  * [rollup](./builder/rollup)

* [react](./react): 基于 React 的前端项目

  * [webpack](./react/webpack): 基于 Webpack 的生产环境项目模板
  * [webpack-ts](./react/webpack-ts): 基于 Webpack & TypeScript 的生产环境项目模板
  * [parcel](./react/parcel): 基于 Parcel 的应用模板
  * [parcel-ts](./react/parcel-ts): 基于 Parcel & TypeScript 的应用模板
  * [patterns](./react/patterns): React 开发模式集锦
  * [jest](./react/jest): 基于 Jest 的单元测试与组件测试
  * [rrv4](./react/rrv4): React Router V4 应用详解
  * [performance](./react/performance): React 性能优化范式
  * [graphql](./react/graphql): GraphQL 客户端实例

* [vue](./vue): 基于 Vue.js 的前端项目

  * [webpack](./vue/webpack)
  * [parcel](./vue/parcel)

* [electron](./electron): 基于 Electron 的跨平台项目

  * [react](./electron/react)
  * [vue](./electron/vue)

* [rn](./rn): 基于 ReactNative 的移动跨平台项目

  * [webpack](./electron/webpack)
  * [webpack-ts](./electron/webpack-ts)

* [State Management](./state): 状态管理

  * [redux](./sm/redux): Redux 典型应用
  * [mobx](./sm/mobx): MobX 典型应用

* [Weapp](./weapp): 微信小程序
  * [mpvue](./weapp/mpvue): 基于 mpvue 的小程序模板
  * [mobx](./weapp/mobx): MobX 模板

* weex: 基于 Weex 的移动跨平台项目(WIP)

