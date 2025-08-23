# Move Zeroes

## Problem Statement
Given an integer array `nums`, move all `0`'s to the end of the array while maintaining the relative order of the non-zero elements.  
You must do this **in-place** without making a copy of the array.

---

## Approach
The algorithm uses a two-pass approach:

1. **First Pass**:  
   - Use a pointer `j` to track the position where the next non-zero element should be placed.  
   - Iterate through the array, and for every non-zero element, place it at index `j` and increment `j`.  
   - Keep a count of how many zeros are encountered.

2. **Second Pass**:  
   - After all non-zero elements are moved to the front, fill the last `count` positions with zeros.  

This ensures the relative order of non-zero elements is preserved and all zeros are shifted to the end.

---

## Time Complexity
- **O(n)** → Each element is processed at most twice.

## Space Complexity
- **O(1)** → No extra space is used; everything is done in-place.
---
# Is Subsequence

## Problem Statement
Given two strings `s` and `t`, return `true` if `s` is a subsequence of `t`, or `false` otherwise.  

A subsequence of a string is a new string generated from the original string with some (can be none) characters deleted without changing the relative order of the remaining characters.

---

## Approach
We use the **two-pointer technique**:

1. Initialize two pointers:  
   - `i` → points to the current character in `s`.  
   - `j` → points to the current character in `t`.

2. Traverse string `t` using pointer `j`:  
   - If `s[i] == t[j]`, move both pointers forward.  
   - Otherwise, move only `j` forward.

3. If pointer `i` reaches the end of `s`, it means all characters of `s` have been found in `t` in order, so return `true`.  
4. If we finish traversing `t` and `i` has not reached the end of `s`, return `false`.

---

## Time Complexity
- **O(n + m)** → `n = length of s`, `m = length of t`.  
- Each string is traversed at most once.

## Space Complexity
- **O(1)** → Only a few pointers are used.
---
# Container With Most Water

## Problem Statement
You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `i`th line are `(i, 0)` and `(i, height[i])`.  

Find two lines that together with the x-axis form a container that can store the most water.  
Return the maximum amount of water a container can store.

---

## Approach
We use the **two-pointer technique**:

1. Initialize two pointers:  
   - `a` at the beginning (`0`)  
   - `b` at the end (`n - 1`).

2. At each step:
   - Calculate the area:  
     `area = min(height[a], height[b]) * (b - a)`  
   - Update the maximum area if needed.  
   - Move the pointer pointing to the **shorter line** inward, since moving the taller one won’t help in increasing area.

3. Continue until the two pointers meet.

This ensures we explore all potential containers in an optimized way.

---

## Time Complexity
- **O(n)** → Each index is visited at most once.

## Space Complexity
- **O(1)** → Only two pointers and a few variables are used.
---
# Max Number of K-Sum Pairs

## Problem Statement
You are given an integer array `nums` and an integer `k`.  
In one operation, you can pick two numbers from the array whose sum equals `k` and remove them from the array.  

Return the maximum number of operations you can perform.

---

## Approach
We solve this using the **two-pointer technique** after sorting:

1. Sort the array `nums`.  
2. Initialize two pointers:  
   - `i = 0` (start)  
   - `j = n - 1` (end).  
3. While `i < j`:  
   - If `nums[i] + nums[j] == k`, we found a valid pair → increment `count`, move both pointers inward.  
   - If the sum is smaller than `k`, move `i` forward to increase the sum.  
   - If the sum is larger than `k`, move `j` backward to decrease the sum.  
4. Continue until the pointers cross.  

---

## Time Complexity
- **O(n log n)** → Sorting takes `O(n log n)`; two-pointer traversal is `O(n)`.  

## Space Complexity
- **O(1)** → No extra data structures used apart from variables.
---
