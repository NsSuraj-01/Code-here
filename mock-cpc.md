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

