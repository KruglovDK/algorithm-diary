# 303. Range Sum Query - Immutable

[LeetCode Link](https://leetcode.com/problems/range-sum-query-immutable/description/)

## Solution

```python
class NumArray:

    def __init__(self, nums: List[int]):
        prefix_nums = [0,]

        for num in nums:
            prefix_nums.append(prefix_nums[-1] + num)

        self.prefix_nums = prefix_nums

    def sumRange(self, left: int, right: int) -> int:
        return self.prefix_nums[right + 1] - self.prefix_nums[left]


# Your NumArray object will be instantiated and called as such:
# obj = NumArray(nums)
# param_1 = obj.sumRange(left,right)
```

## Complexity
### Time
`O(n) & O(1)`
Проходим по массиву, в функции - просто выводим число  
### Space
`O(n) & O(1)`
Аналогично временной оценке  

## Approach
Формируем массив префиксных сумм - в начало массива добавим 0, чтобы не обрабатывать краевые случаи. После, заполняется так, что эл_преф_массива = эл_преф_массива[-1] + эл_базового_массива.
Для получения суммы отрезка мы берем эл-т префиксного массива с индексом, который равен правой границы отрезка (т.е сумма всех чисел до этого элемента) и вычитаем элемент префиксного массива с индексом, который равен левой границе, чтобы вычесть сумму элементов вне отрезка