Combines two different values (of same or different data type). Used by [[Hash Tables]] to insert and retrieve data from them (key-value pairs).

### Syntax
```c++
#include <iostream>
#include <vector>

int main(){
	std::pair <T1, T2> someVar(v1, v2); // where T1 and T2 are data types
	// and v1 & v2 are values of types T1 and T2, respectively.
	T1 key = someVar.first // get key from pair 
	T2 value = someVar.second // get value from pair


}



```

