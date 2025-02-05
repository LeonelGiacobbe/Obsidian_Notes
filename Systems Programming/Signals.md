Simplest form of [[Interprocess Communications]]. `CTRL-C` and `CTRL-Z`, for example.

- Inform processes of events or special conditions
- Handled and sent by the kernel

Sent from [[Processes]] to process, process to itself, or kernel to process

### Causes
- Hardware exception
- Special terminal characters `CTRL-C`
- Software events

### Components
- Defined with unique small integers
	- Specific definition in `signal.h`
- Two Categories: standard and real-time signals
- Delivered ASAP
	- Can be blocked to ensure some blocks of code are not interrupted
		- Done by adding the signal to a process's _signal mask_

### How a process can handle a signal
- Signal is ignored (not common)
- Process is terminated
- Core dump file is generated and process is terminated
	- Core dump is a copy of the memory in a core at the time of failure of a process (used for debugging)
- Process is suspended
- Process is resumed (only _sig cont_)

### System call
> include `signal.h`
- Returns prev signal disposition on success or `SIG_ERR` on failure
- No longer recommended
### Signal sets
- Data structure representing a group of signals
	- `sigset_t` type
- Initializing:
	- `int sigemptyset(sigset_t *set);` 
	- `int sigfillset(sigset_t *set;`
	- Return `0` on success and `1` on failure
- Editing:
	- `sigaddset(const sigset_t *set, int sig)`
	- `sigdeleteset(const sigset_t *set, int sig)`
- Determine if signal is in set:
	- `sigismember`
- 