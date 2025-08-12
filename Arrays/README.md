1. Contains Duplicate Leet Code 217

### Problem
Given an integer array `nums`, return `true` if any value appears at least twice in the array, and `false` if every element is distinct.

### Solutions

#### Method 1: Sorting
- **Time Complexity:** O(n log n)
- **Space Complexity:** O(1)
- **Approach:** Sort the array and check for adjacent duplicates.

#### Method 2: HashSet
- **Time Complexity:** O(n)
- **Space Complexity:** O(n)
- **Approach:** Use a HashSet to track seen elements and detect duplicates quickly.


____________________________________________________________________________________________________________________________________________________________________

2.Longest Subarray with Sum K
###Problem:
  Given an array of integers and a target sum 'k', find the length of the longest contiguous subarray
  that adds up exactly to 'k'.
  
  ###Approach:
  This solution uses the prefix sum technique along with a HashMap to store the first occurrence
  of each prefix sum value.
  
  ###Steps:
  1. Initialize a running sum = 0 and ans = 0.
  2. Traverse the array:
   - Add current element to sum.
   -If sum equals k, update ans to i + 1.
   - If (sum - k) exists in the HashMap, this implies a subarray with sum k exists.
   - Update ans to the maximum of current ans and the subarray length.
   - Store the sum in the HashMap if it's not already there to preserve the earliest index.
  
  ###Why This Works:
  By using the prefix sum concept, we reduce the problem of checking all subarrays to a 
  constant-time lookup using a HashMap. This reduces time complexity from O(n^2) to O(n).
  
  ###Time Complexity: O(n) - Single pass through the array.
  ###Space Complexity: O(n) - For storing prefix sums in the HashMap.
 
  ###Edge Cases Handled:
  - Array contains negative numbers.
  - Multiple subarrays with the same target sum.
  - Entire array itself equals k.
____________________________________________________________________________________________________________________________________________________________________
3. Spiral Matrix Traversal

### Problem Statement

Given a 2D matrix `mat`, return all elements in **spiral order** (clockwise starting from the top-left).

### Approach

Use four boundary pointers (`top`, `bottom`, `left`, `right`) to simulate the spiral traversal of the matrix. Move in a loop through the boundaries, adding elements to the result list in spiral order, and update the boundaries after each traversal.

### Time Complexity

- **O(m × n)**, where `m` is the number of rows and `n` is the number of columns.

### Space Complexity

- **O(1)** (excluding the result list).

____________________________________________________________________________________________________________________________________________________________________
# Valid Sudoku — Java Solution
Problem Statement:  
Determine if a given  **9×9 Sudoku board**  is valid.  
Only the  **filled cells**  need to be validated according to the rules:

i.Each row must contain the digits  `1-9`  without repetition.

ii.Each column must contain the digits  `1-9`  without repetition.

iii.Each of the nine  **3×3 sub-boxes**  of the grid must contain the digits  `1-9`  without repetition.

The Sudoku board  **may be partially filled**, where empty cells are represented by  `'.'`.

Time Complexity: We check each of the 81 cells once → **O(9×9) = O(1) (constant for fixed 9×9 board, or **O(n^2)** generalized).**

Space Complexity: **Three 9×9 arrays → O(1) constant space (or O(n^2) generalized).**
