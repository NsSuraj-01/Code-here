# Problem: Sort Monarchs by Name and Roman Numerals

## Problem Statement
You are given a list of strings, where each string represents the name of a monarch (or other entity) followed by a Roman numeral. The task is to sort these names first by their alphabetical order and then by their Roman numeral values.

## Input
- A list of strings in the format "Name RomanNumeral".

## Output
- A list of strings representing the sorted names.

## Constraints
- The input list is guaranteed to have valid Roman numerals and non-empty names.
- Roman numerals are limited to the range from 1 to 50.

## Example

### Example 1
**Input:**
```python
monarchs = ["Louis IX", "Louis VIII", "Philippe II", "Charles V"]
```
**Output:**
```python
["Charles V", "Louis VIII", "Louis IX", "Philippe II"]
```

### Example 2
**Input:**
```python
monarchs = ["Henry IV", "Henry II", "Henry III", "George VI"]
```
**Output:**
```python
["George VI", "Henry II", "Henry III", "Henry IV"]
```
