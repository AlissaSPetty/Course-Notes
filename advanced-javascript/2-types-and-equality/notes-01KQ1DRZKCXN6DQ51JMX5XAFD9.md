---
runme:
  document:
    relativePath: notes.md
  session:
    id: 01KQ1DRZKCXN6DQ51JMX5XAFD9
    updated: 2026-04-25 14:56:06-04:00
---

### What are the different types in Javascript?

* boolean (T/F)
* number (neg/pos/decimal)
* string (single or double quotes)
* null (a value defined but not given a specific value)
* undefined (a type that has not been defined)
* object (the only non-primitive type)

* `typeOf()` returns the type 

 What is the difference between a static typed language (like Java) and a dynamic typed language (like Javascript)? 
* In static typed languages you have to define your variables as you assign them (`string a = "moo"` would only allow a to be a string, otherwise it would return an error) 
* In dynamic typed languages the type of the value us inferred by whatever is being passed into the variable and can be changed. The type is only defined at runtime.

 What is the difference in null and undefined?
* _undefined_ is returned when a variable is created but not yet assigned a value, therefore not given a type (`var a`) 
  * these are uninitiated values or unknown properties of an object
  * these are set by the JS engine
  * undefined is a value
* _null_ is a defined value given by a variable (`var a = null`) 
  * these are set by programmers 
  * a JS engine will never automatically define null for you
  * null is a value 
  * JS incorrectly reports the type of null as an object

### What is the difference between == and ===?

* == equality checks for type
  * JS is converting both values into the same type (type coercion)
* === strict equality checks for type and value equality
  * if the types on either slice of the equals are different it will *always* return false