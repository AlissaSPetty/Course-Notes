### Dynamic Arrays

* arrays that can grow with your array
* instead of adding one place each time you need to make your array larger, you can double the entire array length making the first additional value interval time O(n), but the additional values (up to your doubled array length) constant time or O(1).

Example: 

  * _Add a new value to an array:_

    [X] = 0(1) 
    [X,X] = O(n) to double the array, then 0(1) to add 1 value

  * _add an additional 3rd value_

    [X,X,X,X] = O(n) to double the array, then O(1) to add up to 2 additional values

  * _add an additional 5th value_

    [X,X,X,X,X,X,X,X] = O(n) to double the array, then O(1) to add up to 3 additional values

  * _add an additional 9th value_

    [X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X] = O(n) to double the array, then O(1) to add up to 7 additional values

  * _add an additional 16th value_

    [X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X,X] = O(n) to double the array, then O(1) to add up to  15 additional values

  etc.

```sh
class DynamicArray {
    // Pointer to store array created using new keyword
    #array;
    // Size of array
    #size;
    // Container size
    #capacity;

    // Default constructor with size 1
    constructor() {
        this.#capacity = 1;
        this.#size = 0;
        this.#array = new Array(this.#capacity);
    }

    // Returns the size of Array i.e Total elements stored currently
    getSize() {
        return this.#size;
    }

    // Returns the size of container
    getCapacity() {
        return this.#capacity;
    }

    // Increase the array size by double of current capacity
    growArray() {
        // Creating new array of double size
        let temp = new Array(this.#capacity * 2);
        this.#capacity = this.#capacity * 2;
        // copy element of old array in newly created array
        for (let i = 0; i < this.#size; i++) {
            temp[i] = this.#array[i];
        }
        // Delete old array
        this.#array = null;
        // Assign newly created temp array to original array
        this.#array = temp;
    }

    isEmpty() {
        if (size == 0) {
            return true;
        }
        else {
            return false;
        }
    }
};
```