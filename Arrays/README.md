# 1.Contains Duplicate Leet Code 217

## Problem
Given an integer array `nums`, return `true` if any value appears at least twice in the array, and `false` if every element is distinct.
Solutions
 
 ## Method 1: Sorting
- **Time Complexity:** O(n log n)
- **Space Complexity:** O(1)
- **Approach:** Sort the array and check for adjacent duplicates.

 ## Method 2: HashSet
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
- **Approach:** Use a HashSet to track seen elements and detect duplicates quickly.


____________________________________________________________________________________________________________________________________________________________________

# 2.Longest Subarray with Sum K
## Problem:
  Given an array of integers and a target sum 'k', find the length of the longest contiguous subarray
  that adds up exactly to 'k'.
  
 ## Approach:
  This solution uses the prefix sum technique along with a HashMap to store the first occurrence
  of each prefix sum value.
  
  ## Steps:
  1. Initialize a running sum = 0 and ans = 0.
  2. Traverse the array:
   - Add current element to sum.
   -If sum equals k, update ans to i + 1.
   - If (sum - k) exists in the HashMap, this implies a subarray with sum k exists.
   - Update ans to the maximum of current ans and the subarray length.
   - Store the sum in the HashMap if it's not already there to preserve the earliest index.
  
 ## Why This Works:
  By using the prefix sum concept, we reduce the problem of checking all subarrays to a 
  constant-time lookup using a HashMap. This reduces time complexity from O(n^2) to O(n).
  
  -Time Complexity: O(n) - Single pass through the array.
  -Space Complexity: O(n) - For storing prefix sums in the HashMap.
 
  ## Edge Cases Handled:
  - Array contains negative numbers.
  - Multiple subarrays with the same target sum.
  - Entire array itself equals k.
____________________________________________________________________________________________________________________________________________________________________
# 3. Spiral Matrix Traversal

## Problem Statement

Given a 2D matrix `mat`, return all elements in **spiral order** (clockwise starting from the top-left).

 ## Approach

Use four boundary pointers (`top`, `bottom`, `left`, `right`) to simulate the spiral traversal of the matrix. Move in a loop through the boundaries, adding elements to the result list in spiral order, and update the boundaries after each traversal.

 ## Time Complexity

- **O(m × n)**, where `m` is the number of rows and `n` is the number of columns.

## Space Complexity

- **O(1)** (excluding the result list).

____________________________________________________________________________________________________________________________________________________________________
# 4.Valid Sudoku — Java Solution
## Problem Statement:  
Determine if a given  **9×9 Sudoku board**  is valid.  
Only the  **filled cells**  need to be validated according to the rules:

i.Each row must contain the digits  `1-9`  without repetition.

ii.Each column must contain the digits  `1-9`  without repetition.

iii.Each of the nine  **3×3 sub-boxes**  of the grid must contain the digits  `1-9`  without repetition.

The Sudoku board  **may be partially filled**, where empty cells are represented by  `'.'`.

## Time Complexity: We check each of the 81 cells once → **O(9×9) = O(1) (constant for fixed 9×9 board, or **O(n^2)** generalized).**

## Space Complexity: **Three 9×9 arrays → O(1) constant space (or O(n^2) generalized).**
____________________________________________________________________________________________________________________________________________________________________
# 5.LeetCode - Rotate Image

## Problem Statement
You are given an `n x n` 2D matrix representing an image, where each element in the matrix is a pixel value. Rotate the image by **90 degrees (clockwise)** in-place.
## Approach
We can solve this problem in **two main steps**:

### 1. **Transpose the matrix**
- Swap `matrix[i][j]` with `matrix[j][i]` for all `i < j`.
- This flips the matrix over its diagonal.

### 2. **Reverse each row**
- For each row, reverse the elements in-place.
- This achieves the 90° clockwise rotation.

### Complexity Analysis
- Time Complexity:

- Transpose: O(n^2)

- Row reversal: O(n^2)

- **Total: O(n^2)**

- Space Complexity:

- **In-place rotation, so O(1) extra space.**
  ---
# Can Place Flowers

## Problem Statement
You are given an array `flowerbed` consisting of `0`s and `1`s, where `0` means empty and `1` means not empty (a flower is already planted).  
You are also given an integer `n`.  

Return `true` if `n` new flowers can be planted in the flowerbed without violating the rule that no two flowers can be adjacent, otherwise return `false`.

---

## Approach
1. Iterate through the `flowerbed` array.  
2. At each position `i`:
   - If the current spot is `0`, check if both its left and right neighbors are empty (or out of bounds).  
   - If both neighbors are empty, plant a flower (`flowerbed[i] = 1`) and increment `planted`.  
3. After processing, compare `planted` with `n`.  
   - If `planted >= n`, return `true`.  
   - Otherwise, return `false`.  

---

## Time Complexity
- **O(n)** → One pass through the flowerbed.  

## Space Complexity
- **O(1)** → Only a few extra variables are used (`planted`, `left`, `right`).  
---
# Kids With the Greatest Number of Candies

## Problem Statement
You are given an integer array `candies` where `candies[i]` represents the number of candies the **i-th kid** has.  
You are also given an integer `extraCandies`.  

For each kid, check if after giving them all the `extraCandies`, they will have the **greatest number of candies among all kids**.  
Return a list of booleans where `result[i] = true` if the i-th kid can have the greatest number of candies, otherwise `false`.

---

## Approach
1. Find the maximum value in the `candies` array (the current greatest number of candies).  
2. For each kid, add `extraCandies` to their candies count.  
3. If this value is greater than or equal to `maxCandies`, mark it as `true`, otherwise `false`.  
4. Store results in a list and return it.  

This approach avoids checking against every kid repeatedly, reducing time complexity.

---

## Time Complexity
- **O(n)** → One pass to find the maximum, and one pass to build the result.  

## Space Complexity
- **O(n)** → To store the result list.  
- Only a few extra variables are used (`max`), so extra space is constant apart from the output list.  
---
