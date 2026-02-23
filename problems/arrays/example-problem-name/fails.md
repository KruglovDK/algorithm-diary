## Attempt 1 — Array index out of range
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
        j = len(nums)
        i = 0
        nums = self.rotateSubArr(nums, i, j)
        nums = self.rotateSubArr(nums, i, k)
        nums = self.rotateSubArr(nums, k, j)
        
```
**What went wrong:** Нужно было добавить k = k % len(nums)
