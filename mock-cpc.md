# 1. Smallest String Problem

## Problem Description

There are \( N \) participants in a race, each with a string containing lowercase letters. Hackbuddy, a curious child, wants to determine the smallest string (both in length and lexicographical order) that **is not a substring** of any of the strings provided by the candidates.

Your task is to find and return this string.

---

## Notes

1. The solution must return the **shortest string** that is not a substring of any of the provided strings.
2. If multiple strings of the same length qualify, return the **lexicographically smallest string**.

---

## Lexicographical Order

- A string \( p \) is lexicographically smaller than a string \( q \) if:
  1. \( p \) is a prefix of \( q \) but not equal to \( q \).
  2. There exists an index \( i \) such that \( p[j] = q[j] \) for all \( j < i \), and \( p[i] < q[i] \).

Examples:
- "abc" < "abcd"
- "abd" < "abec"

---
### Example 1
**Input:**
```python
2
["abc", "bca"]
```
**Output:**
```python
"d"
```

**Explanation:**

The string "d" is the smallest single-character string that does not appear in any of the candidate strings.


---
# 2. Summation Over All Triplets

## Problem Description

You are given the following:

Integers N and Q
Array A of length N
A 2D array operations consisting of Q rows and 4 columns
You need to process Q operations on array A of two types:

Increase each number in the subarray [L, R] by X.
Decrease each number in the subarray [L, R] by X.
After performing all Q operations on array A, find the summation of A[i] + A[j] + A[k] over all triplets (i, j, k) such that 1 ≤ i < j < k ≤ N. Since the answer can be large, return it modulo 10^9+7.

---
## Notes

1. Assume 1-based indexing.
2. A subarray is an array obtained by removing zero or more elements from the front and/or back of the original array without changing the order of the remaining elements.
---

### Example 1
**Input:**
```python
1
5
1 2 3 4 5
3
1 1 3 2
2 2 4 1
1 4 5 3

```
**Output:**
```python
222
```

**Explanation:**

Initial Array: A = [1, 2, 3, 4, 5]
After Operation 1 (Increase [1, 3] by 2): A = [3, 4, 5, 4, 5]
After Operation 2 (Decrease [2, 4] by 1): A = [3, 3, 4, 3, 5]
After Operation 3 (Increase [4, 5] by 3): A = [3, 3, 4, 6, 8]
Finally, calculate the sum of all valid triplets (i, j, k). The result is 222, so the answer is 222.



