>Include `stdlib.h` to use

- `void *malloc(size_t size)`
	- size being bytes in memory
	- returns a pointer to the start of the block or `NULL` on failure
	- Can allocate block of any type thanks to `void *` but need to cast to the appropriate type.