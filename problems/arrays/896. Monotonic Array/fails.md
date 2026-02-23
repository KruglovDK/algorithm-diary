## Attempt 1 — Wrong Answer
```python
class Solution(object):
    def isMonotonic(self, nums):
        """
        :type nums: List[int]
        :rtype: bool
        """
        isIncr = True 
        isDecr = True

        for i in range(1, len(nums)):
            if nums[i] >= nums[i - 1]:
                isDecr = False
            elif nums[i] =< nums[i - 1]:
                isIncr = False 

        return isIncr or isDecr
        
```
**What went wrong:** Использовал >= \ <= вместо строгих сравнений, когда на самом деле это и есть монотонность, т.е пара чисел удовлетворяет условию монотонности и флаги не изменяются.