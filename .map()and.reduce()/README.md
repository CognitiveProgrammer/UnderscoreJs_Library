# Module -2 : Usage of Underscore Js .map() and .reduce() functions

## 1.1 Introduction

__.map()__ and __.reduce()__ is one of the most famous functions of the functional programming and is available in all languages with JavaScript being no exceptions. We do have inbuilt map() and reduce() functions in javascript, we'll see them also along with __undescorejs__ map() and reduce() function

## 1.2 Using .map()

__.map()__ is a mapping function which iterates on each and every element of the JavaScript arrays as well as on objects. One can write generic functions to modify the values of list/arrays and objects.

The __.map()__ function is purely functional as it doesn't change any value of the original list / object itself but always return a new array / object which is generated out of action done on the elements.

### 1.2.1 : Using .map() on arrays

*The first line that must be written before we can use any other underscorejs functions*
```
var _ = require('underscore');
```
*Here is how it will act on arrays. In the example below, the map function will produce a new array by multiplying each and every member of the arr with 2*
```
var arr = [1,2,3,4,5];
var newArr = _.map(arr, function(arrElements){
   return arrElements * 2;
})
```
*The result here will be* __[2,4,5,8,10]__

*As stated earlier, the .map() function is purely functional, so to preserve the conditions of immutability, it will not change the original value, even if we explicitly try to do so. Look at the code below*

```
var arr = [1,2,3,4,5];

var newArr = _.map(arr, function(arrElements){
  arrElements = arrElements + 1;
   return arrElements * 2;
});
```
*Here the original array will remain unchanged and the new array will contain* __[4,6,8,10,12]__

### 1.2.2 Using .map() on JavaScript Objects

*As with arrays, .map() function will also iterate over all keys of the Objects and changes the values as per the expression functions. Here also the original Object will remain unchanged and .map() will provide a new Object.*

*The only change as compared to arrays is that the iterator function will also take* __Keys__ *along with* __Values__ *in the functions. Lets look at the example below*

```
var jsObj = {
  name : "My Name",
  age : 27
};

var newObj = _.map(jsObj, function(objValue, key){
  return  objValue + 2;
});
```
*The newObj will be* __{ name : "My Name2", age : 29 }__

## 1.3 Using .reduce()
The .reduce() function is meant for combining the contents of arrays / objects to come up with a single output.

The .reduce() function generally used with two parameters one contains either the first element of and array / object or the combined output of earlier operations and the next element which need to be combined to form a new value.

### 1.3.1 Using .reduce() with arrays

*Here is the self explanatory code*
```
var arr = [1,2,3,4,5];
var sum = _.reduce(arr, function (first, next) {
  return first + next;
});

```
*The output of the function is* __15__ *which is the sum of all the elements in the array*

*The  .reduce() callback function also have a 3rd parameter which is used rarely. In context of arrays, it will tell the next value index. For the example above, the next index will always contains next value.*
```
var arr = [1,2,3,4,5];
// The nextidex will always contains the index of next value.
var sum = _.reduce(arr, function (first, next, nextindex) {
  return first + next;
});

```

### 1.3.2 Using .reduce() with Objects

*The usage with objects is not that different from arrays where it operates on all values to generate a new one. The keys will be similar to that of indexes. Here is the self explanatory example*
```
var jsObj = {
  name : "My Name",
  age : 27,
  job : "service"
};

var Comb = _.reduce(jsObj, function(firstvalue, nextvalue){
    return  firstvalue + "->" + nextvalue;
});

```
*The output of this function call is* __My Name->27->service__ *which is just the concatenations of all the values in the object*

*Just like in case of arrays, .reduce() also takes a third parameter with its callback function which again is used rarely. it tells the key of next value*
```
// The nextKey will contain the Key of nextvalue in the object
var Comb = _.reduce(jsObj, function(firstvalue, nextvalue, nextKey ){
    return  firstvalue + "->" + nextvalue;
});

```
__That's all about underscorejs .map() and .reduce()__
