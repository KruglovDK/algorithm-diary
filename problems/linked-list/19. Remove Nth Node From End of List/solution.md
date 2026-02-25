# 19. Remove Nth Node From End of List

[LeetCode Link](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

## Solution

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        dummy = ListNode(0, head) # Вводим свою ноду, чтобы не обрабатывать кейс с единственной нодой
        length = 0 # считаем длину в while снизу, чтобы понять, где нужная нода
        curr = dummy

        while curr is not None:
            curr = curr.next
            length += 1
        curr = dummy

        for i in range(length - n - 1): #  по длине доходим до ноды, которая перед нужной
            curr = curr.next
        
        curr.next = curr.next.next # обрываем связь между (нужной - 1) и нужной, заменяя ее на связь между (нужной - 1) и (след.след нодой)
        return dummy.next # возвращаем корректный ответ, не учитывая введенную нами ноду
```

## Complexity
### Time
`O(n)`
### Space
`O(1)`

## Approach

Step-by-step explanation of the solution logic.