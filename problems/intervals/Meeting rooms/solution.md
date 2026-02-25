# Meeting rooms

[Interviewbit Link](https://www.interviewbit.com/problems/meeting-rooms/)

## Solution

```python
class Solution:
    # @param A : list of list of integers
    # @return an integer
    def solve(self, A):
        pairs = []
        for elems in A:
            pairs.append([elems[0], 1])
            pairs.append([elems[1], -1])
        pairs = sorted(pairs)
        max_rooms = 0
        current_rooms = 0
        for pair in pairs:
            current_rooms += pair[1]
            max_rooms = max(max_rooms, current_rooms)
        return max_rooms
```

## Complexity
### Time
`O(nlogn)`
Из-за питоновской сортировки, не считая ее - O(n)
### Space
`O(n)`

## Approach

1. Метод точек. Т.е, мы берем концы интервала, и создаем массив с парами по логике - (нач.инт, 1), (конец инт., -1).
2. Добавляем счетчик рум, занятых сейчас и максимального кол-ва занятых
3. Проходим по массиву с парами, обновляя счетчики
4. значение счетчика max_rooms после выходи из цикла == ответ