- Assumes range of elements is  bounded by `O(n)`
	- If range of elements sort of matches size of array, counting sort is a great choice
- Counts how many elements of each values we have

```
To sort an array A:

initialize array C, elements all zeroes ( # of elements == biggest num in A)

count how many of each element we have:
for j = 1 to A.length
	C[A[j]] += 1

Go through array and add previous element count
for i = 1 to k:
	C[i] = C[i] + C[i-1]
Lets us know how many elements <= to a num

iterate backwards. 
for j = A.length down to 1
	B[C[A[j]]] = A[j]
	C[A[j]] -= 1
basically, for each element in A, go to that position in C, will tell you position of element in sorted array B. Subtract 1 to not overwrite repeats
```