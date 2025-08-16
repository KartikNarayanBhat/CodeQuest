# Strings Roatation Of Each Other

You are given two strings s1 and s2, of equal lengths. The task is to check if s2 is a rotated version of the string s1. 
Note: A string is a rotation of another if it can be formed by moving characters from the start to the end (or vice versa) without rearranging them.

**Input: s1 = "abcd", s2 = "cdab"**
Output: **true**
Explanation: After 2 right rotations, s1 becomes "cdab", which is equal to s2.

## Time Complexity
- Worst-case Time Complexity: **O(n²)**
- Average-case Time Complexity: **Close to O(n)**

## Space Complexity
- Total Space Complexity: **O(n)**
____________________________________________________________________________________________________________________________________________________________________
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
____________________________________________________________________________________________________________________________________________________________________
# String to Integer (atoi)

## Problem Statement
Implement the `myAtoi(string s)` function, which converts a string to a 32-bit signed integer (similar to the C/C++ `atoi` function). The algorithm should:
1. Ignore any leading whitespace.
2. Determine the sign of the number.
3. Read in digits and stop at the first non-digit character.
4. Clamp the integer to the 32-bit signed integer range if it overflows:
   - [-2^31, 2^31 - 1]
5. Return the final integer.

## Approach
1. **Ignore Leading Spaces** – Iterate through the string until a non-space character is found.
2. **Determine Sign** – Check if the next character is `+` or `-` to set the sign.
3. **Convert Digits** – Parse each digit and build the integer value.
4. **Overflow Handling** – Before adding a new digit, check if adding it would cause overflow. If so, return the clamped limit (`Integer.MAX_VALUE` or `Integer.MIN_VALUE`).
5. **Return Result** – Multiply the number by its sign and return it.

## Time Complexity
**O(n)** — where `n` is the length of the string, since we scan each character at most once.

## Space Complexity
**O(1)** — only a few integer variables are used regardless of input size.
____________________________________________________________________________________________________________________________________________________________________
# Find the Index of First Occurrence in String

## Problem Statement
Given two strings `haystack` and `needle`, return the index of the first occurrence of `needle` in `haystack`. If `needle` is not part of `haystack`, return `-1`.
## Approach
We can solve this problem using the **sliding window / substring comparison** technique:

1. Let the length of `haystack` be `n` and the length of `needle` be `m`.
2. Iterate through `haystack` from index `0` to `n - m`.
3. At each step, check if the substring of length `m` starting at the current index matches `needle`.
4. If a match is found, return the current index.
5. If no match is found after traversing the string, return `-1`.
6. 
This approach ensures that we only compare substrings of the exact length of `needle`.

## Time Complexity
- **O(n * m)** in the worst case, where `n` is the length of `haystack` and `m` is the length of `needle`.  
  Each possible starting position (up to `n - m`) may require up to `m` character comparisons.

## Space Complexity
- **O(1)**, as we only use a few variables for iteration and comparisons without extra data structures.
