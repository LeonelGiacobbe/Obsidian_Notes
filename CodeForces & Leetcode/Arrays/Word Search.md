Link: https://leetcode.com/problems/word-search/description/

### Keys to Solve
- Keep a `visited` set to avoid using the same cell twice
	- Add current position to `visited`, perform `dfs` on all adjacent cells, then remove it from the set
- Be careful about bounds for adjacent cells

### Code
```python
class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        rows = len(board)
        cols = len(board[0])
        visited = set()

        def dfs(word_pos, i, j):
            if word_pos == len(word):
                return True
            
            if (i < 0 or i >= rows or j < 0 or j >= cols or 
                (i, j) in visited or board[i][j] != word[word_pos]):
                return False
            
            visited.add((i, j))
            res = (dfs(word_pos + 1, i + 1, j) or
                   dfs(word_pos + 1, i - 1, j) or
                   dfs(word_pos + 1, i, j + 1) or
                   dfs(word_pos + 1, i, j - 1))
            visited.remove((i, j))
            return res

        for i in range(rows):
            for j in range(cols):
                if board[i][j] == word[0]:
                    if dfs(0, i, j): 
                        return True

        return False
```