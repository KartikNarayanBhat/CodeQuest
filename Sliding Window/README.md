# Maximum Average Subarray I

## Problem Statement
Given an array `nums` consisting of `n` integers and an integer `k`, find the contiguous subarray of length `k` that has the maximum average value. Return this maximum average as a **double**.

## Approach
We use the **sliding window technique**:

1. Compute the sum of the first `k` elements.
2. Store this sum as the current maximum.
3. Slide the window one step at a time:
   - Subtract the element that goes out of the window.
   - Add the new element entering the window.
   - Update the maximum sum if the new sum is larger.
4. After processing all windows, divide the maximum sum by `k` to get the maximum average.

This approach ensures we compute the result in linear time without recalculating sums from scratch.

## Time Complexity
- **O(n)**: We traverse the array once, maintaining the sliding window in constant time.

## Space Complexity
- **O(1)**: We use only a few extra variables (`sum`, `max`, indices).
---
# Maximum Number of Vowels in a Substring of Given Length

## Problem Statement
Given a string `s` and an integer `k`, return the maximum number of vowel letters in any substring of `s` with length `k`.

A vowel letter is one of: `'a'`, `'e'`, `'i'`, `'o'`, `'u'`.

---

## Approach
We solve this problem using the **sliding window** technique:

1. Count vowels in the first window of size `k`.
2. Slide the window across the string:
   - Remove the contribution of the character that goes out of the window.
   - Add the contribution of the new character that enters the window.
3. Keep track of the maximum number of vowels found.

This avoids re-checking the entire substring for each window, making the algorithm efficient.

---

## Complexity
- **Time Complexity:** `O(n)`  
  Each character is processed at most twice (once entering the window, once leaving).
- **Space Complexity:** `O(1)`  
  Only integer counters are used; no extra data structures required.
---
# Max Consecutive Ones III

## Problem Statement
Given a binary array `nums` and an integer `k`, return the maximum number of consecutive `1`s in the array if you can flip at most `k` `0`s.

---

## Approach
We use the **sliding window** technique:

1. Maintain two pointers `l` (left) and `r` (right) to represent the current window.
2. Expand the window by moving `r`:
   - If `nums[r] == 0`, decrease `k` (using one flip).
3. If `k` becomes negative (too many `0`s flipped):
   - Shrink the window from the left by moving `l`.
   - If the element at `nums[l]` was `0`, restore a flip by incrementing `k`.
4. Continue until the end of the array.
5. The size of the valid window `r - l` is the maximum consecutive ones.

---

## Complexity
- **Time Complexity:** `O(n)`  
  Each index is visited at most twice (once by `r` and once by `l`).
- **Space Complexity:** `O(1)`  
  Only a few integer variables are used.

---
# Longest Subarray of 1's After Deleting One Element

## Problem Statement
Given a binary array `nums`, return the length of the longest subarray of 1's after deleting exactly one element from the array.  
The deletion can be of either a `0` or a `1`.

---

## Approach
We maintain two counters:
- `cur`: The current streak of consecutive `1`s.
- `prev`: The streak of consecutive `1`s just before the last `0`.
- `ans`: The maximum length found.

Algorithm:
1. Iterate through `nums`.
   - If the element is `1`, increment `cur`.
   - If the element is `0`, update `ans = max(ans, cur + prev)`, then move `prev = cur` and reset `cur = 0`.
2. After the loop, update `ans = max(ans, cur + prev)` (to account for a trailing streak of ones).
3. If the entire array is `1`s, we must delete one element, so return `ans - 1`.  
   Otherwise, return `ans`.

This effectively finds the **maximum length of two consecutive groups of ones separated by a single zero**.

---
