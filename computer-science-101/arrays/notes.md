### Arrays

* Computers use arrays to group data together [ ]
* Arrays start at 0 (called zero index)
  * The last piece of data in an array is always n-1 because of the zero index
* _insertion_ - adding an additional value to an array. Not replacing. 
* linked lists are better for front insertions, and arrays are better for back insertions
* We sacrifice time for memory, which is more useful in larger data sets.

- Fixed Array Runtimes
  - **_inserting into an array at a random position_** - O(n) or linear time
  - **_inserting into the front of an array_** - O(n) or linear time
  - **_inserting into the back of an array_** - 0(1) or constant time
  - **_deleting at the front of an array_** - O(n) or linear time
  - **_deleting at the back of an array_** - O(1) or constant time
  - **_search an unsorted array_** - O(n) or linear time - also known as brute force
  - **_search a sorted array_** - log(n)