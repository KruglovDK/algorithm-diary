# 724. Find Pivot Index

[LeetCode Link](https://leetcode.com/problems/find-pivot-index/description/)

## Solution

```python
class Solution:
    def pivotIndex(self, nums: List[int]) -> int:
        fullSum = sum(nums)
        leftSum = 0

        for i, num in enumerate(nums):
            rightSum = fullSum - leftSum - num
            if leftSum == rightSum:
                return i
            leftSum += num
        return -1
```

## Complexity
### Time
`O(n)`  
### Space
`O(1)`

## Approach
TODO