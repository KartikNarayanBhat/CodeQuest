Reorder List Leet Code - 143 

You are given the head of a singly linked list, and your task is to reorder the list in a specific pattern.
The reordering should follow this rule:
L0 → L1 → L2 → ... → Ln-1 → Ln
L0 → Ln → L1 → Ln-1 → L2 → Ln-2 → ...

head = [1, 2, 3, 4, 5]
[1, 5, 2, 4, 3]


Constraints:
The number of nodes in the list is in the range [1, 5 * 10^4].

1 <= Node.val <= 1000

Approach
The reordering is done in three steps:

Find the middle of the linked list using the slow and fast pointer technique.

Reverse the second half of the list.

Merge the two halves in alternating order.

This is achieved in O(n) time and O(1) extra space.
______________________________________________________________________________________________________________________________________________________________________
