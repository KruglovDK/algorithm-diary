# 560. Subarray Sum Equals K

[LeetCode Link](https://leetcode.com/problems/subarray-sum-equals-k/description/)

## Solution

```python
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        prefix_sum = {0: 1}
        count = 0
        current_px = 0

        for num in nums:
            current_px += num
            if (current_px - k) in prefix_sum:
                count += prefix_sum[current_px - k]
            if current_px not in prefix_sum:
                prefix_sum[current_px] = 0
            prefix_sum[current_px] += 1
        return count

```

## Complexity
### Time
`O(n)`  
### Space
`O(n)`

## Approach
Сильно схоже с two sum, только с подмассивами