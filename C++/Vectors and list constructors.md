---
Created: 2024-02-05T23:06
---
Vectors are defined in the `vector` header.

```C++
\#include <vector>
int main(){    
	// Value initialization (uses default constructor)    
	vector<int> empty{}; // vector containing 0 int elements    
	vector.push_back(45); // adds 45 to the end of the vector    
	return 0;
}
```

To declare a vector in C++: `vector<type> vectorName;` or `vector<type> vectorName(size);`

To access an element of a vector: `vectorName.at(index)` or `vectorName[index]`.

- Similar to lists in Python.
- Able to resize.
- Type stated at declaration.