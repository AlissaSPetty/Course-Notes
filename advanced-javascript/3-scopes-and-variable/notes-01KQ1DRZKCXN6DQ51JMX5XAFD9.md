---
runme:
  document:
    relativePath: notes.md
  session:
    id: 01KQ1DRZKCXN6DQ51JMX5XAFD9
    updated: 2026-04-25 15:12:06-04:00
---

### Scopes and variables

* _scopes_ how long a variable lives before it dies 
  * where that value is visible and available to use in your code

Types of Scopes
* _global_ available anywhere in your code 
  * window actually keeps all defined global variables as properties in the browser
  * global is the value in the node, not window
* _function_ scoped inside the block of the function, not available outside the `{}`
* _block-level_ scoped variables that only exist within that block
  * avaliable in ES6+ 
  * let and const variables 

_variable hoisting_ allows you to call a function or variable before defining it

### What is the scope chain?

* defined by the way the program is written in the file (lexically)
* when calling a variable inside a function the function first looks inside itself, then moves to the outer grandparent
* if the variable is defined below (or after) the function, it will throw an error

### What is IIFE and how would you use it?

_IIFE_ immediately invoked function expression (pronounced if-ee)
* if you have two separate files that both create a global variable at the same time, the file that is references _last_ in your HTML file will be the one that is actually defining the global variable 
* instead of creating a named function, you can instead create an anonymous function by wrapping the function in parenthesis and then calling it immediately by adding another set of empty parenthesis at the end <br>
  * `function() { // code to execute }` <br>
* this makes the function be immediately invoked

### What are function closures? 

* when a function returns a function, the function that is returned then keeps a reference to any variables that it needs to execute
* _closure_ is a special set of references to variables that a function needs in order to execute
* variables that are outside of the function's scope
* closures can refer to variables in outer scopes, and can refer even after those variables have returned 
* best example for interviews <br>
  * `var foo = []` <br>
  * `for(var i=0; i<10; i++){` <br>
      `foo[i] = function() {return i}}` <br>
    `co***********oo[0]) \\10 console.log(foo[i]()) \\10 co***********oo[2]()) \\10`
  * when i is called in this example the val i isn't a copy of i, it's the actual value of i in the outer scope
  * to make this return `0, 1, 2` we need to create an IIFE with a `var y=i` and have `foo[i] = function() return y`