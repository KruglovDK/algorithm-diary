# 206. Reverse Linked List

[LeetCode Link](https://leetcode.com/problems/reverse-linked-list/description/)

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        l = None
        r = head
        while r:
            tmp = r
            r = r.next
            tmp.next = l
            l = tmp
        return l

```

## Complexity
### Time
`O(n)`
  
### Space
`O(1)`