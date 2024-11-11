# Minimum Cost to Cut Chocolate into Single Pieces

## Problem Statement
You are given a chocolate bar represented by a grid of size `n x m`, where `n` is the number of rows, and `m` is the number of columns. The task is to cut this chocolate bar into individual `1x1` pieces. Each cut incurs a specific cost, and the objective is to minimize the total cost of cutting.

Each cut can be made either horizontally or vertically:

- **Horizontal cuts** split the chocolate horizontally, increasing the number of horizontal pieces.
- **Vertical cuts** split the chocolate vertically, increasing the number of vertical pieces.

### Cutting Costs
Each cut has an associated cost:
- `costHor[i]` represents the cost of making the i-th horizontal cut.
- `costVer[i]` represents the cost of making the i-th vertical cut.

The cost of a horizontal cut is proportional to the number of vertical pieces it will affect, and vice versa.

### Objective
To minimize the total cutting cost, always make the most expensive cut available at any point (either horizontal or vertical) to maximize the number of pieces for each cut.

## Input
- An integer `n` representing the number of rows in the chocolate grid.
- An integer `m` representing the number of columns in the chocolate grid.
- An array `costHor` of size `n - 1`, where `costHor[i]` is the cost of making the i-th horizontal cut.
- An array `costVer` of size `m - 1`, where `costVer[i]` is the cost of making the i-th vertical cut.

## Output
Return an integer representing the minimum cost required to cut the chocolate into `1x1` pieces.

## Constraints
- `1 <= n, m <= 1000`
- `1 <= costHor[i], costVer[i] <= 1000`

## Example

### Example 1
**Input:**
```plaintext
n = 4
m = 6
costHor = [4, 1, 2]
costVer = [2, 1, 3, 1, 4]
```
**Output:**
```plaintext
Minimum Cost: 42
```
