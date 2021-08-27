# webpack打包其他资源

## webpack打包样式资源

### webpack的配置文件

创建一个webpack.config.js

基于nodejs平台运行~模块化默认采用commonjs

标准模板：

```js
const { resolve } = require("path");

module.exports = {
  // 入口起点
  entry: "./src/index.js",
  // 输出
  output: {
    //输出文件名
    filename: "built.js",
    //输出路径
    // __dirname 是nodejs的变量名，代表当前文件的绝对路径
    path: resolve(__dirname, "build"),
  },
  // loader 配置
  module: {
    rules: [
      // 详细loader配置
    ],
  },
  // plugins 配置
  plugins: [
    // 详细的plugin配置
  ],
  // 开发模式 development production 
  mode: "development"
};
```

### 打包css文件

```shell
npm i css-loader style-loader -D
```

```js
const { resolve } = require("path");

module.exports = {
  // 入口起点
  entry: "./src/index.js",
  // 输出
  output: {
    //输出文件名
    filename: "built.js",
    //输出路径
    // __dirname 是nodejs的变量名，代表当前文件的绝对路径
    path: resolve(__dirname, "build"),
  },
  // loader 配置
  module: {
    rules: [
      // 详细loader配置
      {
        // 匹配哪些文件
        test: /\.css$/,
        // 使用哪些loader处理
        use: [
          // use数组中的执行顺序，从右到左（倒序执行）
          // 创建style标签，将js中的样式资源插入,添加到head中生效
          "style-loader",
          // 将css 编程commonjs模块加载到js中，里面内容是样式字符串
          "css-loader",
        ],
      },
    ],
  },
  // plugins 配置
  plugins: [
    // 详细的plugin配置
  ],
  // 开发模式 development production
  mode: "development",
};
```



