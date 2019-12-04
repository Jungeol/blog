---
title: nodejs-webpack
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# webpack
모듈 번들러
## install
```
$ npm install -g webpack
```
## set env
```
$ npm install babel-core babel-loader babel-preset-env babel-preset-react babel-preset-stage-0 --save-dev
$ npm install react react-dom --save
```
## set config
index.js가 있는 프로젝트의 루트 폴더에 이 파일을 만들어야 한다.
example
```
# webpack.config.js
const path = require('path')
module.exports = {
    // mode: development, production, none
    mode: 'none',
    // 클라이언트의 시작파일을 지정 모든 의존관계 트리를 자동으로 빌드해준다.
    entry: "./src/index.js", 
    // dist/assets/bundle.js라는 자바스크립트 파일에 출력하라고 지정
    output: { 
        path: path.join(__dirname, "dist/assets"),
        filename: "bundle.js"
    },
    module: {
        // 모듈에 따라 실행히야 하는 로더의 룰을 구성
        rules: [
            {
                // 처리해야할 파일의 정규식
                test: /\.js$/,
                // 제외할 정규식
                exclude: /(node_modules)/,
                loader: 'babel-loader',
                query: {
                    presets: ['env', 'stage-0', 'react']
                }
            }
        ]
    }
}
```
## run
웹팩은 정적으로 실행된다.
보통 앱을 서버에 배포하기 전에 번들을 만든다.
```
$ webpack
```
### mode
mode: development, production, none
- in config
```
module.exports = {
  mode: 'production'
};
```
- pass by CLI
```
webpack --mode=production
```
## source map

```
const path = require('path')

module.exports = {
    mode: 'production',
    entry: "./src/index.js",
    output: {
        path: path.join(__dirname, "dist/assets"),
        filename: "bundle.js",
        // 소스 맵 이릅
        sourceMapFilename: 'bundle.map'
    },
    //소스 맵 사용
    devtool: '#source-map',
    module: {
        rules: [
            {
                test: /\.js$/,
                exclude: /(node_modules)/,
                loader: 'babel-loader',
                query: {
                    presets: ['env', 'stage-0', 'react']
                }
            }
        ]
    }
}
```

