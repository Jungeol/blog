---
title: javascript-sort
date: 2019-12-04 21:40:29
categories:
    - language
    - javascript
tags:
    - javascript
---
# JavaScript Sort
## Notes
- Javascript's sort function is basically sorted by string(even if the value is a number).
```
var arr = [2,12,3,4,1];
console.log(arr.sort());
// [1, 12, 2, 3, 4]
```
- Target Array is sorted in place, and return value is target Array.
```
var arr = [4,5,1,3,2];
arr.sort();
console.log(arr);
// [1, 2, 3, 4, 5]
```
## String Sort

```
var arr = ["a", "c", "b"];
//ASC 오름차순
arr.sort();
arr.sort(function (a, b) { 
    return a < b ? -1 : a > b ? 1 : 0; 
});

//DESC 내림차순
arr.sort().reverse();
arr.sort(function (a, b) {
    return a > b ? -1 : a < b : 1 : 0;
});
```
## Number Sort
```
var arr = [2,1,4,5,3]
//ASC
arr.sort(function (a, b) {
    return a - b;
});
//DESC
arr.sort(function (a, b) {
    return b - a;
});
```
JavaScript's Date object
```
var arr = [
    new Date("2018-02-02"),
    new Date("2018-01-11"),
    new Date("2018-04-11"),
    new Date("2018-05-30"),
    new Date("2018-01-23"),
];
// ASC
arr.sort(function (a, b) {
    return a - b;
});
// DESC
arr.sort(function (a, b) {
    return b - a;
});
```
## Sort by multiple value
```
var arr = [
    {str: "a", num: "3"},
    {str: "b", num: "2"},
    {str: "a", num: "1"},
    {str: "a", num: "2"},
    {str: "b", num: "1"},
    {str: "a", num: "3"}
];

arr.sort(function (a, b) {
    //'str' parameter sotred by asc
    var b1 = a.str < b.str ? -1 : a.str > b.str ? 1 : 0;
    //'num' parameter sotred by desc
    var b2 = b.num - a.num
    //'b1' option is sorted first.
    return b1 || b2;
});

console.log(arr);
// [ { str: 'a', num: '3' },
//   { str: 'a', num: '3' },
//   { str: 'a', num: '2' },
//   { str: 'a', num: '1' },
//   { str: 'b', num: '2' },
//   { str: 'b', num: '1' } ]
```