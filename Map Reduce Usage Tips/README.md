## Module - 2.1 : Some useful tips about map and reduce functions

### 1.1 .Map

* __.map()__ will always return lists whether you pass a list of an object
```
var arr = [1,2,3,4,5];
var ret = _.map(arr, function(val){ return val * 2 });
// ret = [2,4,5,8,10]
```
and for the object

```
var jsObj = {
  name : "Rapid-9",
  age : 27,
  profession : "developer"
};
var ret = _.map(jsObj, function(val){
  return val + "->NewData<-";
});
// ret = [ 'Rapid-9->NewData<-',
'27->NewData<-',
'developer->NewData<-' ]
// which is a list and not an object
```

* __.map()__ callback function can also have more than one parameters which denotes Index as Well as the list itself
```
var arr = [1,2,3,4,5];
// Index will be arr index and list will be the complete list
var ret = _.map(arr, function(val, index, list){
  return val * 2;
});
```
* __.reduce()__ is meant for reducing items into a single item. To do the same it need to access at least 2 items in the callback
* At the first call, the first item is first list element, second item is 2nd list element.
* At subsequent pass, the first item is RESULT of the combination execution between first and second, and second item will be subsequent item in the list
```
var arr = [ 1 ,2 ,3, 4, 5];
var value = _.reduce(arr, function(first, second){
  return first + second;
});
```
*At first pass, first = 1, Second = 2*
*At 2nd pass, first = 3, second = 3*
*At 3rd pass, first = 6, second = 4*
*At 4th pass, first = 10, second = 5*
*At 5th Pass, First = 15, second = nil*
*End of the function*

* Similar to __.map()__, __.reduce()__ also works on Java Script Objects and produces a single combined data

```
var jsObj = {
  name : "Rapid-9",
  age : 27,
  profession : "engineer"
};

var v1 = _.reduce(jsObj, function(first, second){
  return first + second;
});
// v1 = "Rapid-927engineer"

```
* __.reduce()__ can also take multiple parameters in the callback which will the key and the object

```
var v1 = _.reduce(jsObj, function(first, second, key, obj){
  return first + second;
});
```
*The key will be the object key and obj will be the object in consideration*
