---
title: nodejs-babel
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# babel
## 바벨 프리셋
바벨 6은 처리할 수 있는 변환의 종류를 프리셋(preset)으로 나눴다.
개발자는 사용할 프리셋을 지정하여 바벨이 처리할 변환의 종류를 명확히 정의 할 수 있다.
- babel-preset-es2015
    - ES2015(ES6)를 ES5로 컴파일 한다.
- babel-preset-es2016
    - ES2016을 ES2015로 컴파일 한다.
- babel-preset-es2017
    - ES2016을 ES2016으로 컴파일 한다.
- babel-preset-env
    - ES2015, ES2016, ES2017 -> ES5
    - 앞의 세 프리셋을 합친 것
- babel-preset-react
    - JSX를 React.createElement 호출로 변경해준다.

ECMAScript 수용단계를 정할 수 있다.
- Strawman(실험단계): babel-preset-stage-0
- Proposal(제안): babel-preset-stage-1
- Draft(초안): babel-preset-stage-2
- Candidate(후보): babel-preset-stage-3
## install
```
$ npm install --global babel-cli  babel-preset-2015
```
## using
- options
    - -o: file out
    - -w: watch
    - -d: directory
    - --compact=true: code compact
    - --source-maps: source map, {filename}.map file created
```
$ babel test.js -o test.out.js
$ babel src -d dest
src/a.js -> dest/a.js
src/b.js -> dest/b.js
```