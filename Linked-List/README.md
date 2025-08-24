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
______________________________________________________________________________________________________________________________________________________________________
