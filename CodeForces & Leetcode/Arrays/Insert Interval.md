	Link: https://leetcode.com/problems/insert-interval/

### Keys to solve
- Use binary search to find the first position where the first element at that position is not smaller than the first element of the new interval
- Once that is found, append the interval at that index
- Then, use the method in [[Merge Intervals]] to make sure overlapping intervals are stored together, then return the merged list


### Code
```python
class Solution:
    def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
        if len(intervals) == 0:
            return [newInterval]

        low = 0
        high = len(intervals)
        insert_idx = len(intervals) 

        while low < high:
            mid = (low + high) // 2
            if intervals[mid][0] < newInterval[0]:
                low = mid + 1
            else:
                insert_idx = mid
                high = mid

        # Insert newInterval at the determined index
        intervals.insert(insert_idx, newInterval)
            
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