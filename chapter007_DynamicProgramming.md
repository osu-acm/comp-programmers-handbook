Chapter 7: Dynamic programming
===
 * Technique that combines greedy and complete search
 * Can be applied if problem can be divided into overlapping subproblems
 * Used for counting solutions + optimal solution

Coin problem
---
 * Recursively, if coins = {1, 3, 4}, use `solve(x) = min(solve(x-1)+1, solve(x-3)+1, solve(x-4)+1);`
 * `INF` in C++ denotes infinity!
 * Use memoization to speed things up. Memoization just remembers solutions to past sub-problems so we don't have to calculate it again.
 * Both the recursive memoization problem AND the iterative version are DP. 
 * Iteration is better though since it's shorter and often simpler to read.
 * ~~~c++
	value[0] = 0;
	for (int x = 1; x <= n; x++) {
		value[x] = INF;
		for (auto c : coins) {
			if (x-c >= 0 && value[x-c]+1 < value[x]) {
				value[x] = value[x-c]+1;
				first[x] = c;
			}
		}
	}
	while (n > 0) { 
		cout << first[n] << "\n";
		n -= first[n];
	}
   ~~~
 * In order to find the solution as well as the answer, use another array to keep track of the "parent" index. `first` does this.
 * In order to count the number of solutions, use another array as well that stores the count.

Longest increasing subsequence
---
 * Longest subarray that increases between elements
 * Use DP array that keeps track of length. Search for largest length where array[curr] > array[i]. O(n<sup>2</sup>). 
 * There is a O(nlogn) solution though that uses binary search
 * ~~~c++
	for (int k = 0; k < n; k++) {
		length[k] = 1;
		for (int i = 0; i < k; i++) {
			if (array[i] < array[k]) {
				length[k] = max(length[k],length[i]+1);
			}
		}
	}
   ~~~

Paths in a grid
---
 * Find a path from top-left to bottom-right where path is minimized/maximized.
 * Use `sum(row, col) = max(sum(row,col-1), sum(row-1,col)) + value[row][col]`

Knapsack
---
 * Set of objects given, subsets with some properties must be found.
 * Ex: Given a list of weights, find all possible weight combinations.
	* `possible(x, k) = possible(x - wk, k-1) or possible(x, k-1)`
	* Can be done w 1D array by working backwards 

Edit distance
---
 * The minimum number of operations needed to transform a string into another string. Also known as Levenshtein distance.
 * Operations include insertion, remove, or modify.
 * Use `distance(a, b)` where a and b are indices of current string and goal string.
 * `d(a,b) = min(d(a,b-1)+1, d(a-1,b)+1, d(a-1,b-1)+cost(a,b))` where cost(a,b) = 0 if `x[a] == y[b]` else 1.
 * This is representative of min(insert character at end of x, remove character from end of x, modify last character of x).

Counting tiles
---
 * Find # of distinct ways to fill `n` x `m` grid with 1x2 and 2x1 tiles.
 * Use characters to represent different states of each grid space.
 * Go row by row down.
 * Capital pi = Summation but multiplication. There is a surprisingly simple formula to calculate the answer to this problem. Too long to write out though.
