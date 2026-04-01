### Quick Sort
- Divide and conquer approach to sort an array. 
- Choose the left-most value and create two subarrays that sort all remaining values into less than or greater than left-most value. 
- Repeat with left subarray, then right subarray until there are no more subarrays to compare. This has created a tree you can use to sort the array. 


- _Pivot_ - the left-most unsorted value that is used to create subarrays for greater and less than

Runtimes:
- nlog(n) for best case and average case and worst case is n * n or n^2 because things do not always sort evenly. 
- overall this is a faster runtime but the worst case is still just as bad as the other sorts. 
- The number of levels to solve the array grows ar a reverse exponential time. 
  - If we had an array with a length of 8 it would take 3 levels to solve the sort. 
  - If we had an array with a length of 16 it would take 4 levels to solve the sort. 
  - If we had an array with a length of 32 it would take 5 levels to solve the sort. 
  - If we had an array with a length of 64 it would take 6 levels to solve the sort. 

```sh
// partition function
function partition(arr, low, high)
{

    // choose the pivot
    let pivot = arr[high];

    // index of smaller element and indicates
    // the right position of pivot found so far
    let i = low - 1;

    // traverse arr[low..high] and move all smaller
    // elements to the left side. Elements from low to
    // i are smaller after every iteration
    for (let j = low; j <= high - 1; j++) {
        if (arr[j] < pivot) {
            i++;
            swap(arr, i, j);
        }
    }

    // move pivot after smaller elements and
    // return its position
    swap(arr, i + 1, high);
    return i + 1;
}

// swap function
function swap(arr, i, j)
{
    let temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}

// the QuickSort function implementation
function quickSort(arr, low, high)
{
    if (low < high) {

        // pi is the partition return index of pivot
        let pi = partition(arr, low, high);

        // recursion calls for smaller elements
        // and greater or equals elements
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}


// Driver Code
let arr = [ 10, 7, 8, 9, 1, 5 ];
let n = arr.length;

// call QuickSort on the entire array
quickSort(arr, 0, n - 1);
for (let i = 0; i < arr.length; i++) {
    process.stdout.write(arr[i] + " ");
}
```