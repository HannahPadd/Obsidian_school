### Sequential Search
Also called *linear search*
Simplest algorithm possible but also least efficient.
#### Pseudo-code
```
FOR i = 0 TO N-1
	if a[i] = v
		RETURN I
RETURN -1
```
#### C# Implementation
```cs
public int SequentialSearch(int[] arr, int key) {
	for (int i = 0; i < arr.Length; i++) {
		if (key == arr[i]) {
			return i;
		}
	}
	return -1;
}
```
**Performance**
- **O(n)**
- On Average, running time is proportional to the number of elements in the array.
	-  Array of 10 elements -> max. 10 iterations
	- Array of 100 elements -> max 100. iterations
### Binary Search
Standard search algorithm for a **SORTED** sequence
- More efficient that sequential search
- Requires the order of elements
**Basic concept**:
- Divide the sequence in two and focus on the half which could contain the element
#### Pseudo-code (iterative version)
```
low = 0
high = N - 1
WHILE low <= high
	middle = (low + high) / 2
	IF key < arr[middle]
		high = middle - 1
	ELSE IF key > arr[middle]
		low = middle + 1
	ELSE
		RETURN middle
RETURN -1
```
#### C# Implementation (iterative version)
```cs
public int BinarySearch(int[] arr, key) {
	int low = 0;
	int high = arr.Length - 1;
	int mid = 0;
	while (low <= high) {
		mid = (low + high) \ 2;
		if (key < arr[mid]) {
			high = mid - 1;
		}
		if (key > arr[mid]) {
			low = mid + 1;
			}
		else return mid;
		}
	}
```
#### Pseudo-Code (recursive version)
```
BinarySearch(arr, low, high, key)
	IF low > high
		RETURN -1
	middle = (low + high) / 2
	IF arr[middle] > key
		RETURN BinarySearch(arr, low, middle - 1, key)
	ELSE IF arr[middle] < key
		RETURN BinarySearch(arr, midle + 1, high, key)
	ELSE
		RETURN middle
```
#### C# Implementation recursive version)
```cs
public int BinarySearch(int[] arr, int low, int high, int key) {
	if (low > high) return -1;
	middle = (low + high) / 2;
	if (arr[middle] > key) {
		return BinarySearch(arr, low, middle - 1, key)
		}
	if (arr[middle] < key) {
		return BinarySearch(arr, middle + 1, high, key)
		}
	else {
		return middle;
	}
}
```
**Performance**
- **O(logN)**