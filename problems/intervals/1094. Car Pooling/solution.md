# 1094. Car Pooling

[LeetCode Link](https://leetcode.com/problems/car-pooling/description/)

## Solution

```python
class Solution:
    def carPooling(self, trips: List[List[int]], capacity: int) -> bool:
        points = []
        for trip in trips:
            points.append([trip[1], trip[0]])
            points.append([trip[2], -1 * trip[0]])
        points.sort()
        current_fill = 0
        for point in points:
            current_fill += point[1]
            if current_fill > capacity:
                return False
        return True

```

## Complexity
### Time
`O(nlogn)`
Из-за сортировки, без нее - O(n)
### Space
`O(n)`
## Approach
Аналогично Meeting room, только у нас вместо +1/-1 прибавляются/отнимаются кол-во людей. Также добавляется условие выхода при превышении вместимости