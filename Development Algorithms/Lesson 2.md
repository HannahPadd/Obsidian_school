## Sorting

### Stable Sorting
The relative order of similar elements will not change.
### Bubble Sort
Go through the array, compare the current element to the element next to your, if it's higher swap the element. The heavier elements end up at the bottom.
eg.
```
9, 2, 7, 5, 3, 3, 1, 8
2, 9
2, 7, 9
2, 7, 5, 9
2, 5, 7, 9
etc ...
```
Complexity:
- Best Case: **O(n)**
	- Array is already sorted.
- Worst Case: **O(n^2)**
	- Every element needs to be checked.
### Insertion Sort
Start from the second element, compare it to the previous elements, if the element is lower swap them, keep swapping until sorted.

Complexity:
- Best Case: **O(n)**
	- Array is already sorted.
- Worst Case: **O(n^2)**
	- Every element needs to be swapped.

### Merge Sort
Divide and conquer approach. Divide the array until you can't divide it anymore, so up to one element. Then sort the subdivided arrays and then merge them. It is stable.
```
3, 7, 1, 9, 8, 4, 6, 2
//Divide array by (0 + Length) / 2
[3, 7, 1, 9] [8, 4, 6, 2]
//Divide array by (0 + Length) / 2
[3, 7] [1, 9] [8, 4] [6, 2]
//Array can't be divided anymore
//Complexity: O(n^2)
//Merging of the arrays
//Insertion Sort
[3, 7] [1, 9] [4, 8] [2, 6]
//Insertion Sort
[1, 3, 7, 9] [2, 4, 6, 8]
//Insertion Sort
[1, 2, 3, 4, 6, 7, 8, 9]
//Complexity: O(n)
```
*Note:* We aren't actually creating more arrays, just changing the indexes we're working on. 
Complexity:
- **O(n log(n))**
- Complexity does not change, even if the data is already sorted. So it will perform worse than bubble or merge sort.