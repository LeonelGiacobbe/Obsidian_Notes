Link: https://leetcode.com/problems/top-k-frequent-elements/

### Tips to solve
- Make a `number: count` hash map that keep counts of how many times a certain number appeared
- Make a list of lists which will store, at position `i`, a collection of the numbers that appeared `i` times
- Iterate over that list backwards, appending to a `res` list the elements from the right until `len(res) == k`, at which point you return

### Code
```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        # initialize a number: freq hash map
        count = {}
        # This list will store, at position i, what numbers appear i times
        freqs = [[] for i in range(len(nums) + 1)]

        # Build number: freq hash
        for num in nums:
            count[num] = 1 + count.get(num, 0)

        # Get number and frequency, then store freqs[c].append(number that appears c times)
        for n, c in count.items(): # Returns key-value pair
            freqs[c].append(n)

        # since we want the K most frequent values, iterate over array backwards
        res = []
        for i in range(len(freqs) - 1, 0, -1):
            # Append all elements with that frequency, returning if necessary
            for j in freqs[i]:
                res.append(j)
                if len(res) == k:
                    return res
```