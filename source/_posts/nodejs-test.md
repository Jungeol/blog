---
title: nodejs-test
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# unit Test
## 코드검사
1. 동료검토
2. Code linter
3. 코드검사(Code Coverage)
    - Istanbul: 코드의 어떤부분이 테스트로 다뤄지지 않았는지 검사
    - Chai: assrtion 라이브러리
    - Mocha: 테스트 레이아웃 라이브러리
## Mocha
install
```
$ npm install --save mocha
```
run1
```
$ node node_modules/.bin/mocha
```
run2
```
//package.json
{
    ...
    "scripts": {
        "test": "mocha"
    },
    ...
}
```
```
$ npm test
```
## Chai + Mocha
install
```
$ npm install --save chai
```
useage
- run ./test/*.js
```
var module = require("../module");

var chai = require("chai");
var expect = char.expect;

describe("module", function () {
    it("test name 1", function () {
        expect(module("variables1", ...)).to.equal("expectedValue1");
        ...
    });
    it("test name 2", function () {
        expect(module("variables2", ...)).to.euqal("expectedValue2");
        ...
    });
    ...
});
```
mocha before each
```
describe("User", function () {
    var user;
    beforeEach(function () {
        user = new User({
            firstName: "fname",
            lastName: "lname"
        });
    });

    it("something", function () {
        expect(user.getName()).to.equal("fname lname");
    });
    //...
})
```
error test
```
//...
it("throws an error", function() {
    expect(function() { capitalize(123); }).to.throw(Error);
});
//...
```
not
```
//...
if("changes the value", function () {
    expect(capitalize("foo")).not.to.expect("foo");
});
//...
```
# EndPoint Test
## 