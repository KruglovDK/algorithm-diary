# 485. Max Consecutive Ones

[LeetCode Link](https://leetcode.com/problems/max-consecutive-ones/)

## Solution

```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        l = 0
        r = 0
        res = 0
        while l < len(nums):
            while r + 1 < len(nums) and nums[r] == nums[r + 1]:
                r += 1
            if nums[r] == 1:
                res = max(res, r-l+1)
            l = r + 1
            r = r + 1
        return res
```

## Complexity
### Time
`O(n)`
### Space
`O(1)`

## Approach

Аналогично 228