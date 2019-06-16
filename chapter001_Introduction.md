Chapter 1: Introduction
===
* Comp programming is two parts: Design + implementation

General performance tips
---
* Use C++! 80% of comp programmers use it
* Use `g++ -std=c++11 -O2 -Wall test.cpp -o test`
	* -O2 is optimizer flag
	* -Wall shows warnings

* Use `#include <bits/stdc++.h>`to include all STL

* Use `ios::sync_with_stdio(0); cin.tie(0);` to make cin and cout faster!
* Use `freopen("input.txt", "r", stdin); freopen("output.txt", "w", stdout); ` to set redirect stdout/in

* Use macros to do things faster (typedefs, #defines). Kinda advanced.

Introduction to mathematics
---
* Arithmetic progression = Sequence of numbers where difference between 2 adjacent is the same.
	* Formula: n(a+b)/2 where n = length, a = first num, b = last num

* Geometric progression = Sequence of numbers where ratio between 2 adjacent is the same (Ex: 1, 2, 4, 8)
	* Formula: (bk-a)/(k-1) where k = constant ratio

* Harmonic sum = 1 + (1/2) + (1/3) + ... + (1/n) = O(log<sub>2</sub>(n)+1)

* \ = difference between sets (i.e. A \ B)
* N = natural numbers (1-oo), Z = integers (whole nums), Q = rational nums (nums w/o infinite decimal), R = real nums (any num)

* Predicate = something that is T/F based on parameter(s) ex: P(0)
* Upside down A = "for all", backwards E = "there is"

* There is a closed form for Fibonnaci sequence! Called Binet's formula
* A logarithm of x with base b is how many times x needs to be divided by b to get to 1

