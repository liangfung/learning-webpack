## Configuration option -- `output`

> Configuring `output` configuration options tells webpack how to **write the compiled files to disk**.
> `output`配置项控制webpack怎么往硬盘写入编译文件

一个webpack配置中，可以配置多个入口文件，但只能配一个output

output两要素
- filename
- path（绝对路径）

### 多个入口文件 Multiple Entry Points
如果配置了多个chunk, 应使用占位符
```js
module.exports = {
  entry: {
    app: './src/app.js',
    search: './src/search.js'
  },
  output: {
    filename: '[name].js',
    path: __dirname + './dist'
  }
}
// 往硬盘中写入 ./dist/app.js, ./dist/search.js
```

### 高级进阶Adcanced

使用**CDN**和**资源hash**

```js
module.exports = {
  output: {
    path: '/home/proj/cdn/assets/[hash]',
    publicPath: 'http://cdn.example.com/assets/[hash]'
  }
}
```
