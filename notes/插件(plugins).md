# plugins插件

> Plugins are the backbone of webpack

plugins是webpack的支柱功能，目的在于解决loader无法解决的其他事情


## 解剖
一个webpack plugin是一个包含有`apply`方法的**JavaScript对象**。`apply`方法会被webpack compiler调用，并且compiler对象可在整个编译生命周期访问

```js
const pluginName = 'ConsoleLogOnBuildWebpackPlugin'

class ConsoleLogOnBuildWebpackPlugin {
  apply(compiler) {
    compiler.hooks.run.tap(pluginName, compilation => {
      console.log('webpack 构建过程开始！')
    })
  }
}
```

## 配置

webpack.config.js
```js
const HtmlWebpackPlugin = require('html-webpack-plugin')  // to install via npm
const webpack = require('webpack')  // to access built-in plugin
const path = require('path')

module.exports = {
  entry: './path/to/my/entry/file.js',
  output: {
    filename: 'my-first-webpack.bundle.js',
    path: path.resolve(__dirname, 'dist')
  },
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        use: 'babel-loader'
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({ template: './src/index.html' })
  ]
}
```

## Node API
可以使用node api配置webpack的plugin

some-node-script.js
```js
const webpack = require('webpack')  // to access webpack runtime
const configuration = require('./webpack.config.js')

let compiler = webpack(configuration)

new webpack.ProgressPlugin().apply(compiler)

compiler.run(function(err, stats) {
  // ...
})
```