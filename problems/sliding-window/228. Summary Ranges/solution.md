# 228. Summary Ranges

[LeetCode Link](https://leetcode.com/problems/summary-ranges/)

## Solution

```python
class Solution:
    def summaryRanges(self, nums: List[int]) -> List[str]:
        l = 0
        r = 0
        result = []
        # ^ установили указатели и инициализировали рез-щий массив
        while l < len(nums): # двигаем левый, пока не упремся в конец
            while r + 1 < len(nums) and nums[r] + 1 == nums[r + 1]:
                # ^ пока правый на след итерации не укажет на границу
                # ^ И
                # ^ число на которое смотрит правый + 1 равно следующему
                r += 1
                # ^ двигаем правый
            if r != l: # условие задачи - рассм. кейс, если собрался интервал
                result.append(f'{nums[l]}->{nums[r]}')
            else: # условие задачи - кейс, если не собрался интервал, т.е одно число
                result.append(f'{nums[l]}')
            # смещаем оба указателя чтобы пойти по новой
            l = r + 1
            r = r + 1
        return result
```

## Complexity
### Time
`O(n)`
### Space
`O(n)`

## Approach
Описан в коде