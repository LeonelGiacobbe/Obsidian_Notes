---
Created: 2024-02-05T23:04
---
### C++ Templates

Instead of manually creating a bunch of mostly-identical functions or classes (one for each set of different types), we instead create a single _template_. Instead of defining the types for all data  
variables in the function, we use placeholders.  

### Function Templates

A **function template** is a function-like definition that is used to generate one or more overloaded functions, each with a different set of actual types. When we create our function template, we  
use placeholder types (also called   
**type template parameters**, or informally **template types**) for  
any parameter types, return types, or types used in the function body that we want to be specified later. It is done in the following way:  

```C++
template <typename T> // this is the template parameter declaration
T max(T x, T y) // this is the function template definition for max<T>
{    
	return (x < y) ? y : x;
}
```

Now, the max() function can accept parameters of a lot of types (int, double, long, float, etc).

### Naming template parameters

It’s a common convention to use a single capital letter (starting with `T`) when the meaning of that type is trivial or obvious. If a type template parameter has a non-obvious usage or meaning, then a more descriptive name is warranted. There are two common conventions for such names:

- Starting with a capital letter (e.g. `Allocator`). The standard library uses this naming convention.
- Prefixed with a `T`, then starting with a capital letter (e.g. `TAllocator`). This makes it easier to see that the type is a type template parameter.