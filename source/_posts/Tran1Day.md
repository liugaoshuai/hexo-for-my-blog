---
title: 每天一个算法 - 1 - 去重
date: 2017-02-20 21:23:01
tags:
---

### 无序去重

``` javascript
// ES6
var array = [1, 2, 3, 5, 1, 5, 9, 1, 2, 8];
Array.from(new Set(array)); // [1, 2, 3, 5, 9, 8]

// ES5
var arr = [1, 2, 3, 5, 1, 5, 9, 1, 2, 8];

uniqueArrayA(arr); // [1, 2, 3, 5, 9, 8]
uniqueArrayB(arr); // [1, 2, 3, 5, 9, 8]


function uniqueArrayA(arr) {
  var hashmap = {};
  var unique = [];
  for(var i = 0; i < arr.length; i++) {
    if(!hashmap.hasOwnProperty([arr[i]])) {
    //hasOwnProperty() 方法会返回一个布尔值，其用来判断某个对象是否含有指定的属性。
      hashmap[arr[i]] = 1;
      unique.push(arr[i]);
    }
  }
  return unique;
}

function uniqueArrayB(arr){
 var res = [arr[0]];
 for(var i = 1; i < arr.length; i++){
  var repeat = false;
  for(var j = 0; j < res.length; j++){
   if(arr[i] == res[j]){
    repeat = true;
    break;
   }
  }
  if(!repeat){
   res.push(arr[i]);
  }
 }
 return res;
}
```
