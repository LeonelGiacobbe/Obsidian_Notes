Link: https://leetcode.com/problems/spiral-matrix/


### Keys to solve
- For the rows, append the elements in them with `+=`
	- `res += matrix.pop(0) or matrix.pop()[::-1]`
- For the columns, first check that `matrix` is not empty, and the lists inside it are also not empty. Then, iterate over rows and append the last element:
	- `for row in matrix, res.append(row.pop())`
	- `for row in matrix[::-1], res.append(row.pop(0))`

### Code
```python3
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        res  = []

        while matrix:
            # Add first row
            res += matrix.pop(0)

            # Last element of all rows
            if matrix and matrix[0]:
                for row in matrix:
                    res.append(row.pop())

            # Last row in reverse
            if matrix:
                res += (matrix.pop()[::-1])

            if matrix and matrix[0]:
                for row in matrix[::-1]:
                    res.append(row.pop(0))

        return res
```