
### mkdir

`int mkdir(const char *pathname. mode_t mode)`
>include `<unistd.h>` and `<sys/stat.h>`

### rmdir
`int rmdir(const char *pathname)`
> include `<unistd.h>`


### remove
`int remove(const char *pathname)`
> include <stdio.h>
- Can remove both files and directories

### opendir
`DIR *opendir(const char *dirpath)`
> include `dirent.h`
- returns a directory stream on success or NULL on failure

### `dirent` struct
```C
struct dirent {
	ino_t d_ino;
	char d_name[];
}
```
### readdir
`struct dirent *readdir(DIR *dirp)`
>include `<dirent.h>`

- reads next entry in directory
	- needs to be called multiple times to read every entry
- returns pointer to `dirent` structure or `NULL` on end-of-directory
### rewinddir
who tf knows