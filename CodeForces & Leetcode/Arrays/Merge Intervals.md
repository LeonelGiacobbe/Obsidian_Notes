Link: https://leetcode.com/problems/merge-intervals/

### Keys to solve
- Sort intervals in increasing order according to their first element
	- Once this is done, you know that `interval[i][0] >= interval[i-1][0]`, so you can check whether they should be merged or not using their `[1]` element.
- Have a separate array to either merge or append to

### Code
```python
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        # Sort by first element
        intervals.sort(key = lambda interval: interval[0])

        merged = []
        for interval in intervals:
            # if the high end of last interval in merged < low end of curr interval
            # or list is empty
            if not merged or merged[-1][1] < interval[0]:
                merged.append(interval)
            else:
                # Keep the min from the last element, set max to high of last interval in merged
                # or last of current interval
                merged[-1] = [merged[-1][0], max(merged[-1][1], interval[1])]

        return merged
```