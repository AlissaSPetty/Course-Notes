### Merge Sort

- Takes the first 2 values and sorts them, then takes the next 2 values and sorts them. Then takes the first 4 values and sorts them. Repeats the steps for the right side of the array. Finally sorts the right side compared to the left and returns the final sort. 

Runtime: 
- Best, average and worst case is O(n log n). This makes it the fastest comparison of the sort methods.
- The layers of the tree only go up by 1 per log2. 
For example 4 values in an array would be 2 layers to sort through, 8 values would be 3 layers, 16 would be 4 etc. 
No matter how sorted or unsorted each array is, we will always use the same number of steps to sort the array. 

```sh
function merge(arr, left, mid, right) {
    const n1 = mid - left + 1;
    const n2 = right - mid;

    // Create temp arrays
    const L = new Array(n1);
    const R = new Array(n2);

    // Copy data to temp arrays L[] and R[]
    for (let i = 0; i < n1; i++)
        L[i] = arr[left + i];
    for (let j = 0; j < n2; j++)
        R[j] = arr[mid + 1 + j];

    let i = 0, j = 0;
    let k = left;

    // Merge the temp arrays back into arr[left..right]
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    // Copy the remaining elements of L[], if there are any
    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }

    // Copy the remaining elements of R[], if there are any
    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

function mergeSort(arr, left, right) {
    if (left >= right)
        return;

    const mid = Math.floor(left + (right - left) / 2);
    mergeSort(arr, left, mid);
    mergeSort(arr, mid + 1, right);
    merge(arr, left, mid, right);
}


// Driver code
const arr = [38, 27, 43, 10];
mergeSort(arr, 0, arr.length - 1);
console.log(arr.join(" "));
```