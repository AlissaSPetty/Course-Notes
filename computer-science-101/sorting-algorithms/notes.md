### Sorting Algorithms

_Recursion_ - A function that calls itself until the terminating case is reached. If there is no terminating cause the function will call itself until we get a stack overflow error. This happens when we max out the stack memory in out computer. 
- without a terminating value in a while loop it would run forever.
  
_Stable Sort_ - two identical values must be kept in the same position 
_Nonstable Sort_ - order can be removed from the final sort. 
  - Quick Sort and Selection Sort are not stable

| Sorting Algorithms | Best | Average | Worst | 
| --- | --- | --- | --- |
| Bubble Sort | O(n) | O(n^2) | O(n^2) |
| Selection Sort | O(n^2) | O(n^2) | O(n^2) |
| Insertion Sort | O(n) | O(n^2) | O(n^2) | 
| Quick Sort | O(nlogn) | O(nlogn) | O(n^2) | 
| Merge Sort | O(nlogn) | O(nlogn) | O(nlogn)