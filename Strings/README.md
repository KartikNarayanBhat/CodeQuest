# Strings Roatation Of Each Other

You are given two strings s1 and s2, of equal lengths. The task is to check if s2 is a rotated version of the string s1. 
Note: A string is a rotation of another if it can be formed by moving characters from the start to the end (or vice versa) without rearranging them.

**Input: s1 = "abcd", s2 = "cdab"**
Output: **true**
Explanation: After 2 right rotations, s1 becomes "cdab", which is equal to s2.

# Time Complexity
- Worst-case Time Complexity: **O(n²)**
- Average-case Time Complexity: **Close to O(n)**

# Space Complexity
- Total Space Complexity: **O(n)**
______________________________________________________________________________________________________________________________________________________________________
# Reverse String

##  Problem Explanation
Given an array of characters, reverse the array **in-place** (without using extra space for another array).  
This means you have to modify the input array directly so that its characters are in reverse order.

##  Approach
1. **Two Pointers Technique**:
   - Use two variables (`left` and `right`) pointing to the start and end of the array.
   - Swap the characters at `left` and `right`.
   - Move `left` forward and `right` backward.
   - Repeat until `left` is no longer less than `right`.
2. **Why This Works**:
   - Each swap brings the characters into their reversed position.
   - Using two pointers ensures the reversal happens in-place, with **O(1)** extra memory.

##  Time Complexity
- **O(n)** — We need to process each character once (or swap each pair once).

##  Space Complexity
- **O(1)** — No extra array or significant memory is used; only temporary variables for swapping.
___________________________________________________________________________________________________________________________________________________________________
# First Unique Character in a String

## Problem Statement
- Given a string `s`, find the **index** of the first non-repeating (unique) character in it.  
- If there is no unique character, return `-1`.  
- The string contains only lowercase English letters.

  
1. **Count the frequency** of each character using a `HashMap<Character, Integer>`.
   - Iterate through the string and increment the count for each character.
   
2. **Find the first unique character**:
   - Loop through the string again in order.
   - For each character, check if its count is `1` in the `HashMap`.
   - Return the index of the first such character found.

3. **If no unique character is found**, return `-1`.

## Time Complexity
- **O(n)** — We traverse the string twice (`n` is the length of the string).

## Space Complexity
- **O(1)** — Although we use a `HashMap`, it stores at most 26 lowercase English letters, so space usage is constant.

