---
Created: 2024-02-05T23:04
---
To write to files, `include <fstream>`

```C++
\#include <fstream>
//create an ifstream object to read from a file
ifstream infile;
//create an ofstream object to write to a file
ofstream outfile;
outfile << stuff; // cout replaced by outfile
infile >> stuff;  // cin replaced by infile
```

In the example above, `cin` & `cout` get  
replaced by  
`ifstream` & `ofstream`

- `is_open()` checks if a file is open or not. Returns a  
    bool value. Syntax is  
    `file_name.is_open();`
- `file_name.open()` opens a file for reading and  
    writing.  
    
- `file_name.close()` closes the file.
- `.fail()`checks if the reading/writing process  
    failed.  
    
- `.eof()` checks if the previous stream operator reached  
    the end of the file.