Can be shared by processes
### File Mapping
- Maps a region of a file onto the virtual memory of [[Processes]] (like an array)
- File's contents accessed by manipulating memory
- Pages flipped automatically
### Anonymous Mapping
- Used almost exclusively by memory sharing
- Not corresponding to a specific file
- All bytes in that region are mapped to zero.

[[Interprocess Communications]] allow two or more processes to share data