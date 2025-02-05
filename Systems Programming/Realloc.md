> to use, include `stdlib.h`
- `void *realloc(void *ptr, size_t size)`
- Resizes a block of memory
- Returns a pointer to the start of the block on success, `NULL` on failure
- Must always used the value returned from realloc since the block might be moved