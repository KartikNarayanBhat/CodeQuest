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


________________________________________________________________________________________________________________________________________________
2.Set Bits in an Integer

#Problem Statement
Given a positive integer n, the task is to count the number of set bits (1s) in its binary representation.
For example,

n = 5 → binary = 101 → Output: 2

n = 7 → binary = 111 → Output: 3

#Approach
We use bitwise operations to count the number of 1s in the binary form of n:
Use n & 1 to check the last bit.
If it’s 1, increment the count.
Right shift n using n >>= 1 to move to the next bit.
Repeat until n becomes 0.

#Time and Space Complexity
Time Complexity: O(log n)
We check each bit, and there are log₂(n) bits in a number.
Space Complexity: O(1)
Only a few variables are used regardless of input size.
