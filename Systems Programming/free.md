>to use, include `stdlib.h`

- `void free(void *ptr)`
- Deallocates memory pointed to by `ptr`
- Does not reduce the size of the heap
	- Not all freed memory is at the end of the heap
	- Lowers kernel calls (making the program faster)
	- Not always crucial (unless doing deep recursion)

