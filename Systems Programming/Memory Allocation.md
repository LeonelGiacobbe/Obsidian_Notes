### On the heap
- A process allocates memory by increasing the size of the heap
	- The heap being contiguous virtual memory
	- The limit of the heap is called the _program break_

### Usage in C
- Thread safe
- Arbitrary deallocation
- Uses [[Malloc]], [[Calloc]], [[free]] and [[Realloc]]
	- When malloc is called, it scans memory for a contiguous block that is big enough to fit the requested bytes
		- If a block is not found, the program break is extended to fit the bytes.
	- When free is called, the block of memory is added back to the list of available space
	- When malloc allocates a block, a header containing the amount of bytes stored is saved on the bytes preceding the block.