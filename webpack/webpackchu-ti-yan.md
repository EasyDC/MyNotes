# webpack初体验

## 安装

> 需要nodejs

## 初始化项目

```shell
#初始化一个package.json
npm init 

# 安装开发的webpack 和webpack cli
npm i webpack webpack-cli -D 

#创建目录结构
--build #打包产物存放
--src
  --index.js  #文件打包入口
--package.json
```

## 打包一个项目

1. 开发环境打包

   ```shell
   webpack ./src/index.js -o ./build/built.js --mode=development
   ```

2. 生成环境打包

   ```shell
   webpack ./src/index.js -o ./build/built.js --mode=production
   ```

## 小结

1. webpack 能处理js/json 资源 不能处理css/img 等其他资源
2. 生产环境和开发环境能将es5 模块化编译成浏览器识别的模块化
3. 生产环境比开发环境多一个压缩js 的代码



