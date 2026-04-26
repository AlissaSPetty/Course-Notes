### This keyword

* determined by the way a function is called
* if there isn't a calling context _this_ will fall back to global
* `"use strict"` stops the default this object from being the global object
* to fix the issue of _this_ changing which obj is referenced based on context you can _define this as a variable_ at the top of your function and then refer to this keyword as a variable name

### What does the functions call, bind, and apply do?

Stabilizes the _this_ keyword

* in JS functions are actually objects within defined properties
* you can lookup existing properties and create new properties in a function object
* you can call `function.toString()` to return the string of words that make a function object

* `.call()` <br> 
  * operates the same as calling `functionName();` <br>
  * `function a(b,c,d) { console.log(this); console.log(b); console.log(c); console.log(d)}` `a.call(1,2,3,4) \\1,2,3,4` because the first argument in `.call()` is setting the value to _this_ in the function. 

* `.apply()` <br>
  * `a.apply(1[2,3,4])` returns the same values as the code in `.call()` above <br><br>

* use `.call()` unless the function takes a variable number of parameters
* use `.apply()` when calling an array of values <br>
  `function sum(...numbers) {
  let total = 0;
  for (let i = 0; i < numbers.length; i++) {
    total += numbers[i];
  }
  return total;
}`
  * if calling `sum.apply(numbers)` where numbers is an array is the same as `sum.call(1,2,3,4,5)` any value passed to function that is not explicitly assigned is added to the arguments key in the object

  <br><br>
  `.bind()` <br>
  * at the time we _define_ a function expression we can _lock down_ what we want _this_ to be
    * `var a=function() {console.log(this).bind(1), a()}` will always return 1;
  * bind only works with _function expressions_ - setting the function equal to var name, not when you're just writing a function because `.bind()` is applicable to the object that created it

### What is the fat arrow function? =>

=> is primarily used to solve the _this_ problem because it assigns _this_ to the function instead of _this_ being defined as the calling context of the function

_first class functions_ are functions that can be passed around to any other function <br>
  * `setTimeout()`
  * shorthand `let add = (a,b) => a+b`