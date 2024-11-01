---
Created: 2024-02-05T23:05
---
A **non-type template parameter** is a template  
parameter with a fixed type that serves as a placeholder for a constexpr  
value passed in as a template argument.  

A non-type template parameter can be any of the following types: - An  
integral type - An enumeration type -  
`std::nullptr_t` - A  
floating point type (since C++20) - A pointer or reference to an object  
- A pointer or reference to a function - A pointer or reference to a  
member function - A literal class type (since C++20)  

### Defining our own non-type template parameters

Here’s how we define a non-type template parameter:

```C++
\#include <iostream>template <int N> // declare a non-type template parameter of type int named Nvoid print(){    std::cout << N << '\n'; // use value of N here}int main(){    print<5>(); // 5 is our non-type template argument    return 0;}
```

### What are non-type template parameters useful for?