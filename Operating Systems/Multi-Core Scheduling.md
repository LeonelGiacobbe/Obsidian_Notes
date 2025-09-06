- Multi-threading enables better CPU utilization by distributing work across cores.

### Caching
- Hardware caches helps CPUs run faster by keeping recently-used data close.
- To decide what's to be cached, multiple rules are used:
	- Instructions near the current one are probably next
	- Recently executed instructions have a high chance of being executed again

### Possible problems
- Deadlocking:
	- Threads become permanently locked when they are waiting for information that comes from other locked threads, causing circular dependencies.
- Race Conditions:
	- Threads access resources faster / slower than anticipated, breaking synchronization in the program
### Symmetric vs Asymmetric Multiprocessing
- Symmetric:
	- costlier, more complex to design
	- the architecture of each core is the same

### Load Balancing
- Keeps the workload evenly distributed between all processors
- Typically only necessary on systems where each processor has a private queue of processes to execute
- On a common run queue, load balancing is unnecessary, because processors immediately take processes from the queue when they become idle.