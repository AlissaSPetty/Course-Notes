### Insertion Sort
- Takes each individual value out of the array, then inserts tue value into the correct location in the sorted array position. Looks for where it should go. 
- Combines bubble sort and selection sort.
- Similar to how a peron sorts cards.
 
 Runtime: 
 - Similar to bubble sort because it compares two values with each other. n*n/2 = n^2 for average and worst time. 
 Because we are only checking id the extracted value is greater and then moving the cursor, our best time is O(n)

```sh
// Javascript program for insertion sort 

// Function to sort array using insertion sort
function insertionSort(arr) {
    for (let i = 1; i < arr.length; i++) {
        let key = arr[i];
        let j = i - 1;

        /* Move elements of arr[0..i-1], that are
           greater than key, to one position ahead
           of their current position */
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }
}

// A utility function to print array of size n
function printArray(arr) {
    console.log(arr.join(" "));
}

// Driver method
let arr = [12, 11, 13, 5, 6];

insertionSort(arr);
printArray(arr);
```