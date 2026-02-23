# 189. Rotate Array

[LeetCode Link](https://leetcode.com/problems/rotate-array/description/)

## Solution

```python
class Solution:
    def rotateSubArr(self, nums: List[int], i: int, j: int):
        j -= 1
        while i < j:
            nums[i], nums[j] = nums[j], nums[i]
            i += 1
            j -= 1
        return nums

    def rotate(self, nums: List[int], k: int) -> None:
        k = k % len(nums)
        nums = self.rotateSubArr(nums, 0, len(nums))
        nums = self.rotateSubArr(nums, 0, k)
        nums = self.rotateSubArr(nums, k, len(nums))
        
        
```

## Complexity
### Time
`O(n)`
Проходки по массиву  
### Space
`O(1)`
Делал in-place

## Approach
TODO