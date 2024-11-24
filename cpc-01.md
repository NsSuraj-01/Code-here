# CPC - 01

## 1. Trustworthy Subarrays

You are given an array $Arr$ of size $N$ consisting of non-negative integers. Find the number of subarrays of $Arr$, which are trustworthy.

### Definition of Trustworthy Subarray
A subarray is called **trustworthy** if it satisfies the following condition:

The product of the maximum element `max` and the minimum element `min` of the subarray is divisible by the length of the subarray `len`.

### Function Description
Complete the function `solve`. This function takes the following parameters and returns the required answer:

- **N**: An integer representing the size of the array $Arr$.
- **Arr**: An array of non-negative integers.

### Input Format
Use this input format for custom testing or if you are writing code in a language where boilerplate code is not provided:

1. The first line contains $T$, the number of test cases.
2. For each test case:
   - The first line contains a single integer $N$, denoting the size of the array $Arr$.
   - The second line contains $N$ space-separated integers, denoting the elements of $Arr$.

### Output Format
For each test case, print the answer in a new line.

### Constraints
1. $1 \leq T \leq 10$
2. $1 \leq N \leq 5*10^4$
3. $0 \leq Arr[i] \leq 30$

### Example
**Input**:
```python
N: 4
Arr: 5 3 7 19

N: 1
Arr: 7

N: 3
Arr: 17 22 29
```
**Output**:
```python
6
1
5
```


---



## 2. Conditional coordinates
### Problem Description

You are given a rectangle. The bottom-left and top-right coordinates of this rectangle are \((x_1, y_1)\) and \((x_2, y_2)\), respectively.

Also, you are given an arbitrary coordinate \((x_c, y_c)\).

You are required to determine the number of integer coordinates that satisfy the following conditions:
- The points must lie inside or on the border of the rectangle.
- The distance from point \((x_c, y_c)\) must not be greater than \(R\), which is an arbitrary number.

---

### Function Description

Complete the function `solve`. This function takes the following 7 parameters and returns the count of points:

- \(x1\): Represents the \(x\) coordinate for the lower left of the rectangle
- \(y1\): Represents the \(y\) coordinate for the lower left of the rectangle
- \(x2\): Represents the \(x\) coordinate for the upper right of the rectangle
- \(y2\): Represents the \(y\) coordinate for the upper right of the rectangle
- \(xc\): Represents the \(x\) coordinate for the query point
- \(yc\): Represents the \(y\) coordinate for the query point
- \(R\): Represents the maximum distance for the query point

---

### Input Format

**Note**: This is the input format that you must use to provide custom input (available above the Compile and Test button).

- The first line contains four integers x1, y1, x2, y2 (x1 < x2 and y1 < y2).
- The second line contains three integers \(xc, yc, R\).

---

### Output Format

Print a single integer representing the number of **integer coordinates** that satisfy the described conditions.

---

### Constraints

- -10^5 < x_1, y_1, x_2, y_2 < 10^5
- -10^5 < x_c, y_c < 10^5
- 0 < R < 10^5
