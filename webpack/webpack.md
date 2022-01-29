# webpack 4
项目可维护性 拆分模块 借助工具（webpack）
三大框架的脚手架工具都是用webpack作为底层框架的构建
Tree shaking、懒加载、代码分割等

## 初识webpack

面向对象写法
构建node项目
webpack实现面向对象写法es module和commonjs
webpack是什么
webpack官网阅读 module、api var module

webpack是什么
模块是什么
webpack配置文件作用是什么

webpack配置文件写法 entry、  output path
npm script 简化命令代码
webpack-cli作用
webpack文档 get started
webpack打包输出信息 mode、chunks、chunk name

npm install clean-webpack-plugin --save-dev 每次打包先删除之前打包好的文件
npm install html-webpack-plugin --save-dev html 模板文件，并支持写 ejs语法

## webpack核心概念
### loader
### 3

#### 3.1
图片打包 步骤
#### 3.2 图片
loader是什么（webpack本身只能处理js）
loader参数：placeholder
file-loader、url-loader区别 最佳使用方式 自动选择 官网详细介绍

#### 3.3样式

style-loader(Automatically injects styles into the DOM using one <style></style>.)、css-loader 作用
打包流程
sass less stylus样式
如果sass解析报错，检查是否配置sass的webpack打包文件
loader顺序
plugins注意中括号数量
厂商前缀自动添加 postcss-loader 配置
配置autoprefixer时使用到了browsers选项，我是因为没有配置这个选项所导致的没有css浏览器前缀。
[官方建议](https://github.com/browserslist/browserslist#readme)
单独新建一个配置文件```.browserslistrc```或是将配置添加到package.json中。


#### 3.4字体
importLoaders js引入sass和sass中import另一个sass文件区别
css打包模块化
样式冲突 css module
字体文件
iconfont
asset management和sass-loader css-loader style-loader等部分文档

#### 3.5 plugins
htmlWebpackPlugin作用、配置
plugin作用
cleanWebpackPlugin作用、配置

#### 3.6 entry
使用CDN上的js，静态资源配置在CDN上使如何使用
文档中output配置项 entry and contex
仔细阅读output management文档说明
详细配置可以在给出对应github链接里面看到

#### 3.7 SourceMap
如果没有sourcemap，报错位置是打包后的js文件中的错误代码位置
映射关系，dist目录中会多出一个文件
devtool文档中的配置内容
选项
cheap inline module eval
cheap-module-eval-source-map development
cheap-module-source-map production
source-map原理

#### 3.8 WebpackDevServer
webpack脚本
webpack配置
配置
ajax请求必须要在服务器上通过http协议打开，本地文件（file协议）不行
脚手架支持proxy配置，也是因为webpack dev server
自己起一个服务器 express webpack-Dev-middleware 配置server.js
watch、dev server、自己写node起服务
在node中使用webpack、在命令行中使用webpack
command line interface
node.js api
Guides development文档
dev server打包的目录会放在电脑内存里面，而不是dist目录，从而提升打包速度

#### 3.9 Hot module replacement(HMR)
css文件改变时页面不刷新 css-loader底层实现
webpack配置文件改变后需要重启才能生效
如何在js里面实现，不同模块之间互不影响
API、cofiguration和concept中Hot module replacement文档

#### 3.10 babel处理ES6语法
babel preset env语法变更
变量和函数的补充polyfill
useBuiltIns配置实现根据业务代码添加变量和函数，减少mian.js大小
使用useBuiltIns就不需要在业务代码中手动引入polyfill，会自动引入
检查版本选择是否需要babel
在写库项目代码时babel可能污染全局环境，需要配置transform runtime，使用闭包的方式注入变量
如果只是业务代码，只需要配置preset
.babelrc文件是babel文件的配置文件

#### 3.11 react代码打包
未看

### 4

#### 4.1 Tree Shaking
把模块中没有用到的部分都剔除
只支持ES module引入方式，因为ES module是静态引入，而CommonJs是动态引入
配置
Tree Shaking误伤：polyfill本质是在wiindow对象上绑定全局变量，并没有直接导出模块，而被Tree shaking剔除
sideEffects可以免除误伤
引入的模块都会被tree shaking检查
开发环境和发布环境不同

#### 4.2 Development和Production区别
source-map
压缩
tree-shaking
对两种环境配置两个配置文件
配置文件重复代码

#### 4.3 webpack和code splitting
lodash
如果导入外部包，打包文件大，加载时间长；代码如果变更，都需要重新加载
公共代码的拆分 提高代码性能
webpack的插件可以方便的进行code splitting
同步模块引入 异步模块引入

#### 4.4 SplitChunksPlugin
配置参数
chunks
minSize
minChunks
maxAsyncRequests
maxInitialRequests
cacheGroups

#### 4.5 Lazy Loading, chunk
异步引入的模块可以实现懒加载
每个文件是一个chunk

#### 4.6 CSS文件代码分割
miniCssExtractPlugin
css in js
使用环境
fileName chunkFileName

#### 4.7 Shimming
垫片
ProvidePlugin
模块里的this指向
webpack guides

#### 4.8 环境变量的使用
根据环境自动选择配置文件

### 5

#### 5.1 Libraay打包
ES、commonjs、src引入方式
libraryTarget
library
externals ？
npm 上传组件

#### 5.2 Progressive Web Application
http-server
本地缓存 以免断网或者服务器挂掉无法访问
workbox-webpa-plugin
servers-worker原理

#### 5.3 TypeScript的打包配置
提高可维护性和扩展性
superset
ts-loader
@types/lodash
@types/jquery
DefinitelyTyped github

#### 5.4 WebpackDevServer实现请求转发
axios


## 进阶

## 实战案例

## 底层原理及脚手架分析
