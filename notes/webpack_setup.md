本仓库安装的是webpck4.x，所以同时需要安装webpack-cli

```bash
$ npm install webpack webpack-cli -D
```


## 配置文件
webpack4支持无任何配置使用。在使用webpack编译的时候，如果`webpack.config.js`存在，webpack会默认使用这个配置文件。在package.json文件中，可以使用 `webpack --config`来指定webpakc configuration文件。因为实际项目中配置会比较复杂，可能会由几个文件组合而成，名字不一定是webpack.config.js

