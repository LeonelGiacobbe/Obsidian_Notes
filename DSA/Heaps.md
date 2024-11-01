Used to implement priority [[Queues]].
Example of a complete array-based [[DSA/Trees|Trees]].

>[!tip] Accessing Children and parents
>Index of left child of i = `2i + 1`
>Index of right child of i = `2i + 2`
>-------------------------
>>Parent index = `(index of child - 1) / 2`. Round down if needed


### Min Heap
- Parent value is always less than the value of its children
### Max Heap
- Parent value is always more than the value of its children


>[!success] Use heapify to ensure a list follows heap properties
### Inserting into a heap
1) Place item at end of heap
2) Compare value to parent using index formula.
	1) If it doesn't meet the heap property (min / max), swap with parent.
		1) Repeat until you reach the first index of the list
```
void insert(value):
	heap[elements] = value
	
```

### Deleting from a heap
1) Remove first node 
2) Last node in heap becomes first node 
3) Swap first node with its children 
	1) In min heap, with left child 
	2) in max heap, with right child

### Heapify 
1) Start at node `(listSize / 2) - 1`

### BubbleUp
[[C++/Recursion|Recursion]] function to swap indexes (if necessary) until we reach the root 

### BubbleDown 
