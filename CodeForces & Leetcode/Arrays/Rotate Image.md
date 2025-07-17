Link: https://leetcode.com/problems/rotate-image/


### Keys to solve
- Build transpose of image
- After building the transpose, reverse the rows

### Code
```python
from typing import List
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        if not matrix:
            return

        n = len(matrix)

        # Do transpose of matrix
        for i in range(n):
            for j in range(i, n):
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]

        # Reverse rows to finalize image
        for row in matrix:
            row.reverse()
```