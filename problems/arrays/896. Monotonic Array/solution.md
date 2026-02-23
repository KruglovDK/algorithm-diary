# 896. Monotonic Array

[LeetCode Link](https://leetcode.com/problems/monotonic-array/)

## Solution

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
            if nums[i] > nums[i - 1]:
                isDecr = False
            elif nums[i] < nums[i - 1]:
                isIncr = False 

        return isIncr or isDecr
        
```

## Complexity
### Time
`O(n)`
Один раз проходим по массиву
### Space
`O(1)`
Добавлены только две булевых переменных

## Approach
1. По умолчанию считаем, что массив монотонно возрастает и убывает
2. Если нарушается условие возрастания/убывания - заменяем "зеркальный" флаг на false
3. Возвращаем флаги через "or"
4. Можно оптимизировать, сразу возвращая false, если оба флага == false.