# 704. Binary Search

[LeetCode Link](https://leetcode.com/problems/binary-search/description/)

## Solution

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l = 0
        r = len(nums)
        while r - l > 1:
            m = (r + l) // 2
            if nums[m] <= target:
                l = m
            else:
                r = m
        return l if nums[l] == target else -1
```

## Complexity
### Time
`O(logn)`
### Space
`O(1)`