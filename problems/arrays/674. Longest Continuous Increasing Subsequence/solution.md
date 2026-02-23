# 674. Longest Continuous Increasing Subsequence

[LeetCode Link](https://leetcode.com/problems/longest-continuous-increasing-subsequence/description/)

## Solution

```python
class Solution(object):
    def findLengthOfLCIS(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        currentLen = 0
        maxLen = 0
        prev = float('-inf')

        for num in nums:
            if num > prev:
                currentLen += 1
                
            else:
                currentLen = 1

            maxLen = max(maxLen, currentLen)
            prev = num

        return maxLen
```

## Complexity
### Time
`O(n)`
Проходим один раз по массиву  
### Space
`O(1)`
Создаем только переменные

## Approach
1. Инициализируем счетчики текущей и максимальной длины, значение пред. эл-та берем за -бесконечность
2. Проходим по массиву, если текущее число больше предыдущего,текущая длина += 1, иначе = 1.
3. Каждую итерацию проверяем и обновляем максимальную длину, обновляем пред. эл-т