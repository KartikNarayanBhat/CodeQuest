1.Problem Name Unique Number lll (Find the Element That Appears Once (All Others Appear Thrice))

#Problem Statement  :Given an array `arr[]` where every element appears three times except for one element which appears **only once**, find and return that single element.
 Approach

#This problem is solved using **bitwise manipulation** by maintaining two bitmasks:
- `one` stores bits that have appeared once.
- `two` stores bits that have appeared twice.

#The algorithm:
1. For each number:
   - Update `two` with bits that are common in `one` and the current number.
   - XOR the current number with `one` to include new bits.
   - Create a mask to clear bits that appear three times (`one & two`).
   - Apply the mask to both `one` and `two` to reset bits appearing three times.
2. After the loop, `one` contains the unique element.
This method works without using extra memory for a frequency map or array.

#Time and Space Complexity
- **Time Complexity:** O(n) — single pass through the array.
- **Space Complexity:** O(1) — constant space used for bit tracking.
