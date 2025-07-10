Link: https://leetcode.com/problems/non-overlapping-intervals/

### Tips to solve
- Consider three cases:
	- adjacent elements do not overlap
		- Set `prev` pointer to current element
	- adjacent elements overlap partially, like `[1,3] and [2,5]`
		- Increment delete amount by 1, but keep `prev` pointer the same, since the one with the lower high end is more convenient for future checks
	- adjacent element is contained completely within another, like `[1,5] and [2,3]`
		- Set `prev` pointer to current element, since it contains the lower high end. Same reasoning as above.
- Basically, when deleting an interval since two overlap, you want to keep the one with the smallest high end between the two. `[1,3], [2,5] -> delete [2,5]. Set prev to index of [1,3]`. `[1,5], [2,3] -> delete [1,5]. Set prev to index of [2,3]`


### Code
```python
class Solution:
    def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        intervals.sort(key = lambda interval: interval[0])
        end = intervals[0][1]
        prev = 0
        res = 0

        for i in range(1, len(intervals)):
            if intervals[prev][1] > intervals[i][0]:
                if intervals[prev][1] > intervals[i][1]:
                    prev = i
                res += 1
            else:
                prev = i

        return res
```