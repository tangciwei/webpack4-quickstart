#  webpack4学习

> 文章-[React 教程：如何使用 webpack 4 和 Babel 构建 React 应用(2018)](http://www.css88.com/archives/9427)


## 1. 零配置的概念；
>entry point(入口点) 默认为 ./src/index.js
output(输出) 默认为 ./dist/main.js


###  1. 覆盖默认出入口

```json
"dev": "webpack --mode development ./src/index.js --output ./foo/maind.js",
"build": "webpack --mode production ./src/index.js --output ./foo/mainp.js"
```

### 2. module-bind
不通过配置文件使用 babel-loader
```json
"dev": "webpack --mode development --module-bind js=babel-loader"
```

###  3. mode选项
```json
"dev": "webpack --mode development",
"build": "webpack --mode production"
```
生成模式中：开箱即用地进行各种优化。 **包括压缩，作用域提升，tree-shaking**等

## 2. 各种配置
###  1. react结合
.babelrc文件
```json
{
    "presets": [
        "env",
        "react"
    ]
}
```

###  2. 处理html
HtmlWebPackPlugin
```js
{
    test: /\.html$/,
    use: [
        {
            loader: 'html-loader',
            options: {
                minimize: true
            }
        }
    ]
}
```
### 3. csss提取
mini-css-extract-plugin
