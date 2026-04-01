### Bubble Sort
 - starts at the zero position in an array and compares it to position one to see if its larger than position zero. If yes, swap position. Then compares the second position to the third for the larger number and repeats the entire length of the array. This sorts each number by comparing it to its neighbor. 
  - Bubbling up highest number to end and sorting one-by-one at a time
  - Very bad space/time complexity - O(n) - O(n) = O(n^2) - which is an exponential result worst case 
  - a > b else continue (For loop within a for loop)

Example

 | 2 | 7 | 1 | 5 | 3 | 10 |

 7 will shift over until it encounters the 10 

 | 2 | 1 | 5 | 3 | 7 | 10 |

 2 will shift over only 1 time

 | 1 | 2 | 5 | 3 | 7 | 10 |

 5 will shift over only once 

 | 1 | 2 | 3 | 5 | 7 | 10 | 

```sh
BubbleSort(array) {
    for i -> 0 to arrayLength 
        for j -> 0 to (arrayLength - i - 1)
            if arr[j] > arr[j + 1]
                swap(arr[j], arr[j + 1])
}
```

```sh
// Bubble sort Implementation using Javascript

// Creating the bblSort function
function bblSort(arr) {

    for (var i = 0; i < arr.length; i++) {

        // Last i elements are already in place  
        for (var j = 0; j < (arr.length - i - 1); j++) {

            // Checking if the item at present iteration 
            // is greater than the next iteration
            if (arr[j] > arr[j + 1]) {

                // If the condition is true
                // then swap them
                var temp = arr[j]
                arr[j] = arr[j + 1]
                arr[j + 1] = temp
            }
        }
    }

    // Print the sorted array
    console.log(arr);
}

// This is our unsorted array
var arr = [234, 43, 55, 63, 5, 6, 235, 547];

// Now pass this array to the bblSort() function
bblSort(arr);
```