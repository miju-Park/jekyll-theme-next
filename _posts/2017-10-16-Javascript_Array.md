---
title: Javascript에서 유용한 Array 메소드
categories:
 - Javascript
tags:
---

Javascript Array 조작시 사용하면 생산성 향상에 도움이 되는 Method들에 대해 정리

********
* indexOf
  >배열에 해당하는 요소가 포함되어 있는지를 for문 loop를 안돌고 확인하여 해당 인덱스 리턴

[Without **indexof()**]
```javascript
      var arr = ['apple', 'orange', 'pear'], found = false;
      for (var i=0, l = arr.length ; i<l ; i++ ){
        if( arr[i] === 'orange') {
          found = true;
        }
      }
```
[With **indexof()**]
```javascript
      var arr = ['apple', 'orange', 'pear'];
      console.log("found : ", arr.indexOf('orange') != -1);
```
* filter
  > Array의 모든 요소로 해당 function을 수행하여 새로운 array 를 생성

[Without **filter()**]
```javascript
    var arr=[
      {"name" : "apple", "count":2},
      {"name" : "orange", "count":3},
      {"name" : "pear", "count":5},
      {"name" : "orange", "count":1},
    ];

    var newArr = [];

    for(var i=0, l=arr.length ; i<l ; i++) {
      if(arr[i].name === 'orange') {
        newArr.push(arr[i]);
      }
    }
    console.log("filter result : ", newArr);
```
[With **filter()**]
```javascript
    var arr=[
      {"name" : "apple", "count":2},
      {"name" : "orange", "count":3},
      {"name" : "pear", "count":5},
      {"name" : "orange", "count":1},
    ];

    var newArr = arr.filter(function(item) {
      return item.name === 'orange';
    });

    console.log("filter result : ", newArr);
```
* forEach
  > Array의 모든 요소를 돌면서 해당 함수를 실행한다.<br>
  > for문이 forEach보다 성능상 낫다고 하지만 차이가 미미하고 몇 ms를 줄이는 것이 생산성 향상보다 우선시 되지 않아 forEach 를 가급적이면 쓸것

[Without **forEach()**]
```javascript
    var arr = [1,2,3,4,5];

    for( var i=0, l=arr.length; i<l ;i++) {
      console.log(arr[i]);
    }
```
[With **forEach()**]
```javascript
    var arr=[1,2,3,4,5];
    arr.forEach(function(item, index) {
      console.log(item);
    });
```
*map

 > Array의 모든 요소에 대해 해당 함수를 수행한 결과로 새로운 Array를 생성.

[Without **map()**]
```javascript
    var oldArr = [
      {first_name: "Colliln", last_name: "Toh"},
      {first_name: "Addy", last_name: "Osmni"},
      {first_name: "Yehuda", last_name: "Katz"}
    ];

    function getNewArr() {
      var newArr = [];
      for(var i=0, l=oldArr.length ; i<l ; i++) {
        var item = oldArr[i];
        item.full_name = [item.first_name, item.last_name].join("");
        newArr[i] = item;
      }
      return newArr;
    }
    console.log(getNewArr());
```
[With **map()**]
```javascript
    var oldArr = [
      {first_name: "Colliln", last_name: "Toh"},
      {first_name: "Addy", last_name: "Osmni"},
      {first_name: "Yehuda", last_name: "Katz"}
    ];

    function getNewArr() {
      return oldArr.map(function(item, index) {
        item.full_name = [item.first_name, item.last_name].join("");
        return item;
      });
    }
    console.log(getNewArr());
```
* reduce

  >배열을 왼쪽에서 순회하면서 single 값으로 reduce 하기 위한 함수<br>
  Array.reduce(callback함수, 초기값)<br>
  callback 함수는 (prev, current, currentIndex, array) 매개변수를 받음.<br>
  배열을 순회하면서 callback함수에서 반환되는 값이 다음 prev 값으로 감

[Without **reduce()**]
```javascript
    var arr = ["apple","orange","apple","orange","pear","orange"];
    function getWordCnt() {
      var obj={};

      for(var i=0, l=arr.length; i<l; i++) {
        var itm = arr[i];
        obj[item] = (obj[itm] +1) || 1;
      }
      return obj;
    }
    console.log(getWordCnt());
```
[With **reduce()**]
```javascript
    var arr = ["apple","orange","apple","orange","pear","orange"];
    function getWordCnt() {
      return arr.reduce(function(prev,next){
        prev[next] = (prev[next]+1) || 1;
      }, {});
    }

    console.log(GetWordCnt());
```
    