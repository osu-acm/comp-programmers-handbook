Chapter 8: Amortized analysis
===
 * Method to determine time complexity
 * Estimate total time for all operations, not specific ones

Two pointers method
---
 * Subarray sum (find subarray w sum s) = Two pointers, one start, one end. Each iteration, start pointer moves forward 1, end moves until sum > s.
 * Ex: `[1, 3, 2, 5, 1, 1, 2, 3], s = 8` . 
	* Starts with `1, 3, 2` since the next element makes it > 8.
	* Moves over 1. Now `3, 2`. Still `5` would make it exceed 8.
	* Moves over 1. Now `2`. Add `5`. Add `1`. Now found solution!
 * 2SUM (find two elements in array that sum to s) = Sort, one start, one end. Each iteration, start moves forward 1, end moves until pair < s.

Nearest smaller elements
---
 * Use a stack to solve this problem. Push items to stack, then pop off the stack when the top of the stack is greater than the current element.

Sliding window
---
 * A subarray that moves from left to right. Generally used for strings.
 * Ex: Find the minimum sum of elements in a 4-length subarray.
 * Use queue to do this :D 
