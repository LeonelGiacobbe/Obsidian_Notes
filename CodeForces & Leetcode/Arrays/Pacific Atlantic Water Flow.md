Link: https://leetcode.com/problems/pacific-atlantic-water-flow/

### Keys to solve:
- Have two sets, one for coords that can get to the Atlantic, and another for the Pacific.
- We know every element in the first row, and the first element of every row can get to the pacific. We know that the last row and the last element of every row can get to the Atlantic.
	- From that, we run `dfs` on every one of those elements, visiting the adjacent elements, and adding them to the corresponding set if the adjacent value is greater than the current value.
- For final return statement, use `list(a.intersection(b))

### Code
```python
class Solution:
    def pacificAtlantic(self, heights: List[List[int]]) -> List[List[int]]:
        ROWS, COLS = len(heights), len(heights[0])
        get_to_pac = set() # 1st list, 1st element of every list
        get_to_atl = set() # last list, last element of every list

        def dfs(r, c, visited, prevHeight):
			# check if we already visited this location,
			# bounds are correct, and if the curr height < prev
			# remember we're going from the ocean in, so curr < prev
			# means water cannot flow, don't add to set
            if ((r,c) in visited or 
                r < 0 or c < 0 or r == ROWS or c == COLS or 
                heights[r][c] < prevHeight):
                    return

            visited.add((r, c))

            dfs(r - 1, c, visited, heights[r][c])
            dfs(r + 1, c, visited, heights[r][c])
            dfs(r, c - 1, visited, heights[r][c])
            dfs(r, c + 1, visited, heights[r][c])

		# First and last rows, with respective sets
        for c in range(COLS):
            dfs(0, c, get_to_pac, heights[0][c])
            dfs(ROWS - 1, c, get_to_atl, heights[ROWS - 1][c])
		# First and last columns, with respective sets
        for r in range(ROWS):
            dfs(r, 0, get_to_pac, heights[r][0])
            dfs(r, COLS - 1, get_to_atl, heights[r][COLS - 1])

        return list(get_to_pac.intersection(get_to_atl))
```