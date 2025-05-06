 Contains Duplicate Leet Code 217

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

