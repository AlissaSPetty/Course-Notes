### What is Destructuring and Looping?

* _Destructuring_ is a way to extend values into variables from data stored in objects or arrays 
  * `const obj = {first: 'alissa', last: 'petty', age: '35'}` <br> destructured `const{first: f, last: l} = obj`
* you can shorthand first:first to first like `const {first} = obj;`
  * `const arr=['a','b'];` <br> destructured `const[x=arr[0]];` <br> shorthand `const[x,y]=arr;`
* im a function you can declare the destructured arguments 
  * `function f({x}{console.log(x)}; f({x=1}));`
* if nothing is passed into the function as an argument you can give you destructured value a default value function 
  * `f({x=0}{ //code })`
  * `f({})` if no default you get an error

### LOOPS

* _breaks_ when reached in the code immediately exit
* _continue_ when reached in the code do not execute the code after the continue statement

#### What are the 4 loops?

  1. **for loop** <br> allows breaks and allows continues <br>
    `for(let i=0; i<arr.length; i++);` 

  2. **for each loop** <br> does not allow breaks or continues <br> can use return to exit out of inner functions but not the outer functions <br>
    `forEach(function(value))`

  3. **for in** <br> loops over _obj_ properties
    `for(let prop in obj)`

  4.  **for of** <br> loops over array <br> will return actual value <br> allows breaks and continues
    `for(let index of array)`