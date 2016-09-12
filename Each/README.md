# Module -1 : Usage of Underscore Js .each() functions

## 1.1 Installing Underscore Js library

Its pretty easy to install Underscore Js library via npm. Please follow the instructions present http://underscorejs.org for installation.

## 1.2 Including Underscore Js inside your JavaScript source code

The source code usage _require()_ function to include the code into JavaScript source. Its usual practice to declare the variable as '\_', but any other variable name can also be used instead.
```
var _ = require('underscore');
```

## 1.3 Using \_.each() function for JavaScript arrays

The first usage of \_.each() function is with arrays. As the name suggest, it will not only iterate over an array but will also provide you the index of array as well as complete array within the functional block.

Here is the code which is self explanatory

```
var _ = require('underscore');

var listArr = [1,2,3,4,5];

_.each(listArr, function(value, index, theArray){
  console.log("The value at index ", index, " is -> ", value);
  console.log("The whole array is ", theArray);
});

```
## 1.4  Using \_.each() function for JavaScript Object

Just like arrays \_.each() function could also be used for JS objects. The difference as compared to list is that while the __value__ remain the value, the index becomes the __Key__, and 3rd parameter becomes the __object__ itself.

Here is the code that demonstrates the usage with objects
```
var _ = require('underscore');

var jObj = {
  name: "Software Engineer",
  age : 27,
  occupation: "Service",
  at : "MNC"
};

_.each(jObj, function(value, key, ObjectItself){
  console.log("The first Object Key is ->", key, "  And the Value is -> ", value);
  console.log("The object itself is -> ", ObjectItself);
});

```
## 1.5 Using \_.each() for JS objects with functions

The JavaScript Object which we have seen earlier contains plain key value pairs. As with JavaScript objects, the value of some keys could be functions itself. It will be interesting to note that since we're having objects, we can implicitly use it to invoke the function at each iterations
```
var jObjAndFns = {
    myList : [1,2,3,4,5,6,7],
    PrintSomeThing : function () {
      console.log("I am actually printing somethings");
    }
};

_.each(jObjAndFns, function(value, key, theObject){
    console.log("Key -> ", key, " :  Value -> ", value);
    theObject.PrintSomeThing();
});
```

## 1.6 Using the context of \_.each() function
In \_.each() callback function, the 3rd parameter is always the first parameter being passed in .each() function. In case of above object __jObjAndFns__, if weant to pass the list __myList__ then we have to use the context to access the member functions.
Here is the code that demonstrates the same

```
_.each(jObjAndFns.myList, function(value, index, list) {
  console.log("The index is -> ", index, " Value -> ",value);
  jObjAndFns.PrintSomeThing();
}, jObjAndFns);
```
*In the above example, the 3rd parameter of each() which is the context is used for calling Object functions.

In this we don't need to call the object by name, we can use* __this__ *instead as demonstrated below*
```
_.each(jObjAndFns.myList, function(value, index, list) {
  console.log("The index is -> ", index, " Value -> ",value);
  this.PrintSomeThing();
}, jObjAndFns);

```

__That's all about basic usage of \-.each()__
