### What is Javascript
* TC39 group reviews proposals to decide what should be a Javascript standard
* ECMAscript is a document that explains what features are available in different versions of the document
* Javascript is 100% compatible with any website built in Javascript and can be used regardless of when it was created


### Compiling vs Polyfill
**Compiler** allows you to write the latest version of Javascript code and then the compiler turns that latest code into older code that is readable by the browser
* Babel is a very common compiler xand had a website that shows you how new code is compiled
  * Examples: 
    * the _let_ variable compiles to _var_ variable 
    * newer Javascript allows line breaks, Babel compiles those line breaks into \n

**Polyfill** allows you to _import_ a feature into your code using a package.
* Once imported you can use the feature in the same way you would without needing to late compile the code 
  * Examples: 
    * Promise has a promise promise Polyfill that can be added to Javascript

Both the compiler and polyfill solve the same problem, just in different ways. 
