Chapter 10: Bit manipulation
===
 * Computers use binary to represent data

Bit representation
---
 * Use two's complement for negative numbers: 1's are 0's and 0's are 1's
 * Can get two's complement really easily by converting negative `int` var to `unsigned int` var

Bit operations
---
 * `&` = AND
 * `|` = OR
 * `^` = XOR
 * `~` = NOT
 * `<<` or `>>` are bit shifts, adds 0's to each side.
 * `x ^ (1 << k)` inverts the `k`th bit of `x`
 * `__builtin_clz(x)` gets number of zeros at beginning of `x`
 * `__builtin_popcount(x)` gets number of ones

Representing sets
---
 * Use 32-bit type to represent a set {0..31} where each bit reps a num
 * Very useful for intersect, union, complement, difference, etc. due to just needing a single bit operation between two ints to ge them.
 * Go through subsets of x: `b = 0; do{}while (b = (b-x)&x);`.

Bit optimizations
---
 * Hamming distance = length of number of positions where two strings differ
 * Problem: Find minimum hamming distance between two strings in list of strings
	* If length of string is small and only two characters, use `__builtin_popcount(a ^ b);` - Almost 30 times faster
 * Problem: Given `n` x `n` grid where each square is black or white, get subgrids where all corners are black
	* Use `__builtin_popcount(color[a][i]&color[b][i]);` with N 64-bit representations.

Dynamic programming
---
 * Bit operations are convenient for storing state representations in dynamic programming problems
 * Problem: Given k products over n days, have to buy all products but only one per day.
	* Did not understand the solution to this problem
 * Change iteration over permutations to iteration over subsets
 * Problem: Elevator with max weight `x`, `n` people want to go up. Minimum number of rides?
	* Classic knapsack problem.
	* For each subset, calculate minimum number of rides AND minimum weight of people in last group

