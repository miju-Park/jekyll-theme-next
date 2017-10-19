---
title: Javascipt Tips
categories:
 - Javascript
tags:
---
Javascript Coding Tips

********

*  Nested Data Structure 처리시 주의사항

Object 에 Key를 추가할 때 key 의 name 을 모르는 경우라면 *[]* notation을 써야함 (dot notation X)

* 숫자처럼 생긴 문자열을 숫자로 처리하는 방법
```javascript
var X = '12345'
console.log(typeof X); //string

console.log(typeof +X); //number
```
