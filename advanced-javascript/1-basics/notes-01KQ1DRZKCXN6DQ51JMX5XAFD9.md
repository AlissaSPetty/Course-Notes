---
runme:
  document:
    relativePath: notes.md
  session:
    id: 01KQ1DRZKCXN6DQ51JMX5XAFD9
    updated: 2026-04-25 14:55:57-04:00
---

### What is Javascript

* TC39 group reviews proposals to decide what should be a Javascript standard
* ECMAscript is a document that explains what features are available in different versions of the document
* Javascript is 100% compatible with any website built in Javascript and can be used regardless of when it was created

### Compiling vs Polyfill

**Compiler** allows you to write the latest version of Javascript code and then the compiler turns that latest code into older code that is readable by the browser
* Babel is a very common compiler and had a website that shows you how new code is compiled
 * Examples:
    * the _let_ variable compiles to _var_ variable
    * newer Javascript allows line breaks, Babel compiles those line breaks into \n

__Polyfill__ allows you to _import_ a feature into your code using a package.
* Once imported you can use the feature in the same way you would without needing to late compile the code
 * Examples:
    * Promise has a promise promise Polyfill that can be added to Javascript

*Both the compiler and polyfill solve the same problem, just in different ways.*

### use strict
* always written as a string
* allows you to place a program or a function into a strict operating context
* makes debugging easier
  * calling a variable before it has been defined causes an error - this helps in debugging because if you typo your declared variable later in the code the JS browser will throw an error at the typo location bc that typo is not yet defined
  * you cannot use words that are reserved by future versions of JS - ex: you cannot use var ket as a variable because it is a reserved word
  * you cannot delete functions, variables or function arguments - ex: `var foo = 1; delete foo` would error because you cannot delete variables
  * you cannot declare or redeclare variables in eval() - any var in `eval(" ")` is only accessible in `eval()`
    * _eval_ allows you to evaluate a JS expression by passing in a string - variables created in `eval(" ")` leak out of eval mode - this happens when a var is redefined in eval after being originally defined higher in the code

### Does JS pass variables by reference or value?

* primitive types (string/number/bool) are passed by values
* objects are passed by reference

 pass by value
  * if you change the val of a primitive type inside a function, the changes won't affect the variable in the outer scope 
  * variable defined outside of the function them manipulated inside a function won't change the variable because you pass in a _copy of the variable in the function and not in the actual value of the variable_

 pass by reference
  * when you change a property of that object from within the function _the change will be reflected in the outer scope_
  * you are not passing in a copy, you're passing in the actual value that points to that objects
  * you cannot change what it actually points to, you can only change a property in the object
    ex: `var a = {'moo': too} function foo(a) {a = {'too': 'moo'}}` would return the value `'moo: too'` but if you instead `console.log()` a property inside the function you would get the additive value in the object `a.too = moo` would output `{moo: 'too', too: moo}`;

### What are rest operators?

* compresses a number of _single elements_ into an array
* although you can use `.length()` to loop over the arguments in a function, the argument properties are not actually an array. (args are the params passed into a function)

* to use `.slice()` in an argument list you need to first change the argument into an array by creating a variable and setting its value to `array.prototype.slice.call(arguments, number)`
* instead of using `array.prototype()` you can use the rest operator to call the argument values by setting the arg to `...options` - this collapses all args into an array which opens args to allow values to use array values/features like `.slice()` or `.push()`

* the rest operator has to be the last value called because it encompasses all values in the argument
* when `console.log()` arguments in a function, any value before the rest operator calls the values up to the point of the rest. 
  * `function login(method, ...options)` <br> `{console.log(method); \\val` <br> `console.log(options)} \\2,3,4` <br> `login('val', 2,3,4)`

### What is the slice operator?
* takes a _single array value_ and explodes it into a number of single _elements_
* `ar**y1=[4,5,6] ar**y2=[1,2,3, ...ar**y1]` <br>
`co**************y2) \\[1,2,3,4,5,6]` <br>
but if you didn't use the spread operator in `ar**y2` you would get  `[1,2,3, ar***(3)]`
* unlike the rest operator, you can put the spread operator anywhere in the array
* replaces `.concat()` in the array
* copies an array to another array, so if you later manipulate the original array the spread will still return the initial values in the array <br>
  `arr1=[1,2,3] arr2=[...arr1] arr1[0]=-1` <br>
  `co************r1) \\[-1,2,3]` <br>
  `co************r2) \\[1,2,3]`

### What are template strings? (template literals)
* allows you to add variables between the special characters
* also allows you to use expressions between template tags 
  * for styled components the tad is created using backticks with css inside and the where tag is referenced later in the file applies the styles
* also used in i18n accessibility to use translated values inside the tag value passed inside the string
* `function h1******gs, ...values) {` <br> 
  `var body= ''; var name='alissa'; var place='world';` <br> 
  `fo******=0; i<strings.length, i++ {body+=strings[i]})` <br>
`co**********h1 hello ${place}, my name is ${name}) \\<h1>Hello world my name is al**sa.</h1>` <br> `}`
