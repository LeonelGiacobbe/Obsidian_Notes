Link: https://leetcode.com/problems/number-of-islands/


### Keys to solve
- Iterate over the whole grid
- Once you find a `1`, activate `dfs`, where you'll find all adjacent `1`s and mark them as `0`.
	- This saves the need from using a hash set to mark visited locations
- After the `dfs` is completed and you keep iterating, if you find another `1` that means it was not connected to the previous one, meaning its a new island.

```python
class Solution:
    def numIslands(self, grid: List[List[str]]) -> int:
        visited = set()
        rows = len(grid)
        cols = len(grid[0])

        def dfs(i, j):
            if i < 0 or i >= rows or j < 0 or j >= cols or grid[i][j] != "1":
                return
            else:
                grid[i][j] = "0" # Mark it as "visited"
                dfs(i-1, j)
                dfs(i+1, j)
                dfs(i, j-1)
                dfs(i, j+1)

        islands = 0
        for i in range(len(grid)):
            for j in range(len(grid[0])):
                if grid[i][j] == "1":
                    islands += 1
                    dfs(i, j)

        return islands
```