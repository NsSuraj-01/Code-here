# Code-here


Coding Challenge: Maximum Substring Frequency

*Problem Statement*

You’re given a sequence called a _pointer_, composed solely of lowercase letters from the English alphabet.

Imagine creating all potential combinations of strings using lowercase English characters. For each possible string, determine the number of times the pointer fits into it as a seamless substring (i.e., without any gaps). Consider even cases where the pointer might overlap multiple times within the same string.

Your task is to find the maximum number of times the pointer can appear as a substring within any string of a given length, _combination_. In other words, find the highest possible value of X, where X represents the maximum frequency of the pointer appearing as a substring in a composite string of _combination_ letters.

Input

	•	pointer: A string composed of lowercase English letters. (1 <= length <= 100)
	•	combination: An integer representing the length of the composite string. (1 <= combination <= 10,000)

Output

	•	Return an integer representing the maximum number of times the pointer can appear as a substring in a composite string of the specified combination length.

Example Cases

Example 1

Input:

pointer = "wxyzz"
combination = 6

Output:

1

Explanation:
For any 6-letter combination, the substring “wxyzz” can only appear once. There are no 6-letter strings where “wxyzz” appears more than once.

Example 2

Input:

pointer = "xbzxcxbdxzx"
combination = 22

Output:

3

Explanation:
One of the strings of length 22 could contain exactly three occurrences of “xbzxcxbdxzx” through overlapping placements, maximizing the frequency of the pointer in the string.

Constraints

	•	The pointer string length is up to 100 characters.
	•	The combination length can be very large (up to 10,000), so consider efficiency in your solution.

Instructions

	1.	Fork this repository to start working on the problem.
	2.	Implement your solution.
	3.	Submit your solution by creating a pull request to this repository.
