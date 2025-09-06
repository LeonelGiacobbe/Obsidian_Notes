Link: https://leetcode.com/problems/set-matrix-zeroes/

### Keys to solve:
- You only care about the zeroes that were in the original matrix
- Iterate over the matrix, find all coords where the element is zero, add to list
- Iterate over the elements of the list, and change the entire row and column to zero

### Code
```python
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        coords = []

        for i in range(len(matrix)):
            for j in range(len(matrix[0])):
                if matrix[i][j] == 0:
                    coords.append((i, j))

        
        for coord in coords:
            for i in range(0, coord[0]):
                matrix[i][coord[1]] = 0
            for i in range(coord[0], len(matrix)):
                matrix[i][coord[1]] = 0

            for j in range(0, coord[1]):
                matrix[coord[0]][j] = 0
            for j in range(coord[1], len(matrix[0])):
                matrix[coord[0]][j] = 0
            
```