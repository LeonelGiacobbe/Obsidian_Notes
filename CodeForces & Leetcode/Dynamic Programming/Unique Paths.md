Link: https://leetcode.com/problems/unique-paths/

### Keys to solve:
- Assume there's one way to get to the starting cell
	- From that, we can assume there's only one way to get to any cell that is in the same row or column as the starting cell
- For every other cell, the amount of ways to get to it is the sum of the values in the cells to the left and up
	- Since robot can only move up or down, we are only concerned about those two positions

```python

class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        # in robot's starting row and column, ways is one
        # then for every row, possibility is val(up) + val(left)

        ret = []
        for i in range(m):
            ret.append([0] * n)

        ret[0][0] = 1

        for i in range(m):
            for j in range(n):
                if i == 0 and j == 0: # top left
                    continue
                elif i == 0: # top row
                    ret[i][j] = ret[i][j - 1]
                elif j == 0: # left column
                    ret[i][j] = ret[i - 1][j]
                else:
                    ret[i][j] = ret[i][j - 1] + ret[i - 1][j]

        return ret[-1][-1]
```