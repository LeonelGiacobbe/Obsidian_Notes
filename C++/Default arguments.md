---
Created: 2024-02-05T23:04
---
A **default argument** is a default value provided for a  
function parameter. For example:  

```C++
void print(int x, int y=10) // 10 is the default argument
{    
			std::cout << "x: " << x << '\n';    
			std::cout << "y: " << y << '\n';
}
```

When making a function call, if an argument is not specified, the  
default value for that argument will be used.  

### When to use default arguments

Default arguments are an excellent option when a function needs a  
value that has a reasonable default value, but for which you want to let  
the caller override if they wish.  

If a parameter is given a default argument, all subsequent parameters  
(to the right) must also be given default arguments.  

The following is not allowed:

```C++
void print(int x=10, int y); // not allowed
```

### Default arguments can not be redeclared

For a function with a forward declaration and a function definition,  
the default argument can be declared in either the forward declaration  
or the function definition, but not both. Best practice is to declare  
the default argument in the forward declaration and not in the function  
definition, as the forward declaration is more likely to be seen by  
other files (particularly if it’s in a header file).  

### Default arguments and function overloading

Functions with default arguments may be overloaded (see [[Function Overloading]]). For example, the following is allowed:

```C++
\#include <string>
void print(std::string){
}
void print(char=' '){
}
int main(){    
	print("Hello, world"); // resolves to print(std::string)    
print('a'); // resolves to print(char)    
print(); // resolves to print(char)    return 0;
}
```