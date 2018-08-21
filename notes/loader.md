loader用于对模块的源代码进行转换。可以在`import`或'load'module的时候预处理文件

## loader怎么写
loader模块需要导出为一个函数


## 特性
- loader支持链式传递
- loader可以是同步的，也可以是异步的
- loader运行在node.js中
- loader接收查询参数，用于对loader传递配置
- 普通的npm模块可以导出为loader，做法是在`package.json`加上`loader`字段
- plugin可以为loader带来更多特性
- loader可以产生额外的任意文件