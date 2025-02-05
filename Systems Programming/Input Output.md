### Types of files
- Standard
- Devices (peripherals)
- Pipes (inter-process comms)
- Sockets (network comms)
- Directories


### File descriptors
- Every file has a unique ID for each process
	- streams in `C++`, file pointers in `C`
	- `0`, `1` and `2` are mapped to `stdin`, `stdout` and `cerr` respectively

### System calls for file I/O
- `open (pathname, flags, mode)`
	- include `sys/stat.h` and `fcntl.h`
	- returns file descriptor if successful
	- `mode`: permissions (for when creating a file)
	- `flags`: read, write, append, etc. Can be used to create a file if it doesn't exist
- `read (fd, buffer, count)`
	- A specified amount of bytes, stored in a buffer. Returns amount read
	- `buffer` : memory to read into
	- `count` amount of bytes to read
- `write(fd, buffer, count)`
	- A specified amount from buffer and returns amount written
	- `fd`: the file descriptor we want to use
	- `buffer`: location of memory to write
	- `count`: max number of bytes to write
- `close(fd):
	- Closes the file using descriptor, releasing that number and its resources
	- After closing, the file descriptor `fd` becomes invalid


### Blocking vs Non-Blocking
- Blocking calls wait until the desired resource becomes available
- Non-blocking calls don't wait. They either execute if the resource is available or fail if it's not