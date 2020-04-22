---
title: javascript-map_reduce_filter
date: 2019-12-04 21:40:29
categories:
    - language
    - javascript
tags:
    - javascript
---
# map, reduce, filter
## Array.prototype.map
구문
```
arr.map(callback[, thisArg])
```
- callback 매개변수
    - currentValue: 현재 요소
    - index: 인덱스
    - array: 대상 Array
- thisArg: callback시 this로 활용되는 값
사용법1
```
[1, 2, 3, 4].map(function (value) { return value * 2; });
// [2, 4, 6, 8]
["1", "2", "3", "4"].map(Number);
// [1, 2, 3, 4]
```
사용법2
```
//Array.prototype.map;
[].map.call("Hello WOrld", function(x) { return x.charCodeAt(0) });
//[ 72, 101, 108, 108, 111, 32, 87, 79, 114, 108, 100 ]
```
## Array.prototype.reduce
구문
```
arr.reduce(callback[, initialValue]);
```
- callback 매개변수
    - accumulator : 
        - initialValue이 존재하면 해당 값으로 초기화
        - 이후 callback의 return 값으로 대체
    - currentValue : 현재 값
    - currentIndex : 현재 값의 Index
    - array : 대상 Array

사용법1
- initialValue 생략
- currentIndex = 1 부터 시작
```
var arr = [0, 1, 2, 3, 4];
var res1 = arr.reduce(function (acc, curr, idx, arr) { return acc + curr; });
// sum of arr values : 10
var res2 = arr.reduce((acc, curr) => Math.max(acc, curr));
// max of arr values : 4
```
사용법2
- initialValue 활용
- currentIndex = 0 부터 시작
- accumulator = initialValue 로 초기화
```
var arr = [[0, 1], [2, 3], [4, 5]];
var res = arr.reduce((acc, curr) => acc.concat(curr), []);
// [0, 1, 2, 3, 4, 5]
```
```
var arr = [
    { id: 0, name: "Adams" }, 
    { id: 1, name: "Edwards" }, 
    { id: 2, name: "Nelson" }
];
var res = arr.reduce(function (acc, curr) {
    acc[curr.id] = curr.name;
    return acc;
}, {});
// { 0: "Adams", 1: "Edwards", 2: "Nelson" }
```
## Array.prototype.filter
구문
```
var new_array = arr.filter(callback[, thisArg]);
```
- callback:
    - element
    - index
    - array
- thisArg: callback의 this로 사용하는 값

사용법
```
var result = [1, 2, 3, 4, 5].filter(function (value) { return value > 3; });
// [4, 5]
```