- Real time: from a standard point or fixed point
- Process time: amount of CPU time used by [[Processes]]

### Calendar Time
- Time since January 1, 1970 UTC at midnight
- Stored in type `time_t`
- `#include <time.h>`

### Software clock
- Measures time in `jiffies`
	- Length of each `jiffy` is based on the `hz` variable in the kernel
		- Configurable when compiling the kernel, with `250` as the default (5ms)
### Process time
- User CPU time: for [[Processes]] run in user mode
### Time call
`time_t time(time_t *timep)`
> include `time.h`
- Often used with `NULL` to avoid segmentation violation
- Returns seconds since epoch or -1 on failure

### Ctime
`char *ctime(const time_t *timep)`
>include 
### Gettimeofday
`int gettimeofday(struct timeval *tv, struct timezone *tz)`
>include `sys/time.h`

### Struct timeval

``` C
struct timeval {
	time_t tv_sec // Time since epoch
	suseconds_t tv_usec // Additional microseconds
}
```