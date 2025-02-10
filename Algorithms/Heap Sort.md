> `n log n` time complexity
- A Divide and Conquer algorithm
```
BUILD-MAX-HEAP(Array)

for i = A.length down to 2
	exchange A[1] with a [i]
	A.size = A.size - 1
	MAX-HEAPIFY(A,1)
```

### For a node `i` in a heap
- Index of parent is `floor(i/2)`
- Left child is `2 * i`
- Right child is `(2 * i) + 1`
### Max heapify
- The parent of a node is always `>=` its children
- Has a `O(nlogn)` cost
- Can take a regular heap and make it into a max heap with `MAX-HEAPIFY`
	- Call with a `for i = floor(heap.length / 2) down to 1`
- ![[Pasted image 20250210123838.png]]


### Exercuse