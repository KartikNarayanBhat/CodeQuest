# Subsets

## Problem Statement
Given an integer array `nums` of unique elements, return all possible subsets (the power set).

The solution set must not contain duplicate subsets. You may return the solution in any order.

---

## Approach
This problem is solved using **backtracking**:

1. Start with an empty subset.
2. At each step, iterate through the array starting from the current position `p`.
3. For each element:
   - Add it to the current subset (`temp`).
   - Recursively generate all subsets that include this element.
   - Backtrack by removing the last added element to explore other possibilities.
4. Add a copy of the current subset (`temp`) to the result list at each recursive call.

This way, all possible combinations of elements are generated.

---

## Time Complexity
- **O(n × 2^n)**  
  - Each of the `2^n` subsets is generated.  
  - Copying each subset into the result takes up to `O(n)` time.  

## Space Complexity
- **O(n)** (excluding the output)  
  - The recursion stack can go as deep as `n` (number of elements).  
  - The result list will contain `2^n` subsets, which is required output space.
