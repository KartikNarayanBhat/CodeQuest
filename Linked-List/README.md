# Reorder List

##  Problem Statement
You are given the head of a singly linked list, and your task is to reorder the list in the following pattern:
L0 → L1 → L2 → ... → Ln-1 → Ln
L0 → Ln → L1 → Ln-1 → L2 → Ln-2 →

### Constraints
- The number of nodes in the list is in the range `[1, 5 * 10^4]`.  
- `1 <= Node.val <= 1000`  

---

##  Approach
The reordering is done in three main steps:

1. **Find the middle of the linked list**  
   - Use the slow and fast pointer technique to locate the middle node.  

2. **Reverse the second half of the list**  
   - Reverse the list starting from the middle to the end.  

3. **Merge the two halves**  
   - Alternate nodes from the first half and the reversed second half to form the reordered list.  

---

##  Complexity
- **Time Complexity:** `O(n)` → Each step (finding middle, reversing, merging) takes linear time.  
- **Space Complexity:** `O(1)` → Only pointers are used, no extra data structures.  

---
#  Partition List

##  Problem Statement
Given the `head` of a linked list and an integer `x`, partition the list so that:  
- All nodes with values **less than `x`** appear before nodes with values **greater than or equal to `x`**.  
- The original **relative order** of the nodes in each partition is preserved.  

Return the head of the modified linked list.  

---

##  Approach
- Use two dummy lists:  
  - `before` list for nodes `< x`.  
  - `after` list for nodes `>= x`.  
- Traverse the original linked list and place each node into the correct list.  
- Connect the `before` list with the `after` list.  
- Return the head of the `before` list.  

---

##  Complexity
- **Time Complexity:** `O(n)` → each node is processed once.  
- **Space Complexity:** `O(1)` → only a few pointers are used.  


This is achieved in O(n) time and O(1) extra space.
____________________________________________________________________________________________________________________________________________________________________
# Reverse Linked List II

## Problem Statement
Given the `head` of a singly linked list and two integers `left` and `right` where `left <= right`,  
reverse the nodes of the list from position `left` to position `right`, and return the modified list.  

- Positions are **1-indexed**.  
- The reversal must be done **in-place** without creating new nodes.  

---

## Approach
1. Traverse the list until reaching the node at position `left`.  
   - Keep track of the node before it (`connection_node`) and the current node at `left` (`tail`).  
2. Reverse the sublist between `left` and `right` using the standard linked list reversal method.  
   - Update pointers (`prev`, `current_node`, `next_node`) for `n = right - left + 1` steps.  
3. Reconnect the reversed sublist back into the original list:  
   - If `connection_node` exists, connect it to the new head of the reversed sublist (`prev`).  
   - Otherwise, update `head` to `prev`.  
   - Connect the tail of the reversed sublist (`tail`) to the remaining part (`current_node`).  
4. Return the new `head`.  

---

##  Time Complexity
- **O(n)** → Single traversal of the linked list.  

##  Space Complexity
- **O(1)** → Only a few pointer variables are used; no extra data structures.  

