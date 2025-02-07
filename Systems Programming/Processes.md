- Instance of a program executed in memory
- Managed by the kernel, who handles various information:
	- User
	- Process ID (PID)
	- Termination Status
	- Parent Processes

### Parts of a process
- The instruction text (machine code that is being executed)
- Global and static variables
- Heap (dynamically allocated memory)
- Execution stack
### System calls
- `fork` clones a process and creates a child
	- Returns `0` on the child, a positive integer in the parent, and `-1` on failure
- `exit` terminates
- `wait` suspends current process and waits for child to terminate
- `exec` loads a program into memory