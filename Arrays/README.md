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
