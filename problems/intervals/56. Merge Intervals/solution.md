# 56. Merge Intervals

[LeetCode Link](https://leetcode.com/problems/merge-intervals/description/)

## Solution

```python
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        intervals.sort()
        result_intervals = [intervals[0]]
        for interval in intervals:
            if max(interval[0], result_intervals[-1][0]) <= min(interval[1], result_intervals[-1][1]):
                result_intervals[-1][1] = max(result_intervals[-1][1], interval[1])
            else:
                result_intervals.append(interval)
        return result_intervals
```

## Complexity
### Time
`O(n)`
### Space
`O(n)`

## Approach

1. Факт пересечения наступает (overlapping) при: max(a1,a2) <= min(b1, b2). a = начало интервала, b = конец интервала
2. Пересечение интервалов - у результирующего обновляем правую границу на max(b1, b2), оставляя левую, т.к мы отсортировали интервалы. Без сортировки левая граница - min(a1,a2)
3. Изначально кладем в результирующий массив первый интервал, чтобы не обрабатывать его через if