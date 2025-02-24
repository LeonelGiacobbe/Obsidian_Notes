>Time complexity `O(n+m)`
- Creates another array of arrays
- Assigns elements from array A to sub-arrays in B
- Sorts each sub-array in B.
- Worst case scenario, every element goes into the same bucket, resulting in a `O(n^2)` complexity
```
sort (A)
let B be an array [0..n-1]
n =length(A)
for i = 0 to n-1
make b[i] an empty list

for i = 1 to n
insert A[i] into B[floor(n*A[i])]

sort each element (array) in B
```