### Selection Sort

 - Always looks for the lowest unsorted value and swaps the lowest unsorted position. 
 - Another nested for loop
 - When writing the code you are alway keeping track of the min number and rewriting that var as it compares.

To sort: 
- compare each position to the current lowest number in the array then add the lowest number for the entire array to the largest unsorted position. 
- The lowest number in an array would swap positions with whatever is in the first position of the current array. 
- Repeat and compare the next lowest value and swap whatever is in the second position with that number and repeat until all numbers are sorted.

Runtime: 
- n/2 * n = n^2 for all cases 
- slightly worst whan Bubble 

```sh
function selectionSort(arr) {
    let n = arr.length;
    for (let i = 0; i < n - 1; i++) {
    
        // Assume the current position holds
        // the minimum element
        let min_idx = i;
        
        // Iterate through the unsorted portion
        // to find the actual minimum
        for (let j = i + 1; j < n; j++) {
            if (arr[j] < arr[min_idx]) {
            
                // Update min_idx if a smaller element is found
                min_idx = j;
            }
        }
        
        // Move minimum element to its
        // correct position
        let temp = arr[i];
        arr[i] = arr[min_idx];
        arr[min_idx] = temp;
    }
}

function printArray(arr) {
    for (let val of arr) {
        process.stdout.write(val + " ");
    }
    console.log();
}

// Driver function 
const arr = [64, 25, 12, 22, 11];

console.log("Original array: ");
printArray(arr);

selectionSort(arr);

console.log("Sorted array: ");
printArray(arr);
```