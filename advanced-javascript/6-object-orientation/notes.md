### Object Oriented Programming (OOP)

### What is the prototype chain?

* every object will inherit from _one other_ object
* in the console you can link and object to a prototype by using `var._proto_=value`
* you can check to see if one obj is a prototype of another object with the `isPrototyeOf()` function
* lookups are dynamic - updating a property that previously only existed on the prototype of an object adds it to the object and not the prototype


* `object.create()` creates a new object and assigns the passed argument as the prototype of the object 
  * this is more commonly used than \_proto_ assigning
  * this also allows you to add additional objects as passed arguments
    * `object.create(animal, {food: value: "mango"})`
    * when adding additional objects you're not adding an object to use as the properties, you're _describing_ the properties
    * you're setting the key as food and the value as mango
  * `object.create(proto[,properties object])`