---
Created: 2024-02-05T23:05
---
A reference is an alias for an existing object. Applying an operation to a reference also applies the operation to the object it is referencing.

### Lvalue reference types

An lvalue reference type acts as an alias for an existing lvalue (see [[Value categories (lvalues and rvalues)]]). To declare an lvalue reference type, we use an ‘&’ immediately following the type of an object. For example:

```C++
int& ref // lvalue reference type to an int object.
```

### Lvalue reference variables

We can also create an lvalue reference variable. This variable acts as a reference to another lvalue (usually another variable).

```C++
int x { 5 }; // int variable
int& ref { x }; // reference variable to x
```

### Modifying values through lvalue references

Aside from reading a value through an lvalue reference, we can also modify that value:

```C++
int x { 5 }; // int variable
int& ref { x }; // reference variable to x
std:: cout << x << ref << endl; // prints 55
ref = 6;
std:: cout << x << ref << endl; // prints 66
x = 7;
std:: cout << x << ref << endl; // prints 77
```

### Initialization of lvalue references

References must be initialized. We cannot create a reference to a variable that does not yet exist.

It is common practice to say that a reference is _binded_ to an object. That process is called _reference binding_. The object or function being referenced is called the referent.

We can’t create a reference to a const or constexpr variable.

In most cases, the type of the reference must match the type of the variable being referenced.

### References can’t be reseated (changed to refer to another object)

Read above :)

### lvalue reference scope and duration

Reference variables follow the same scope and duration that normal variables do.

### References and referents have independent lifetimes

- A reference can be destroyed before the object it is  
    referencing.  
    
- The object being referenced can be destroyed before the  
    reference.  
    
- Destroying a reference does not destroy the variable it was  
    referencing.  
    

### Dangling references

When the object being referenced is destroyed before the reference, the reference is said to be a dangling reference.

### Side notes

- References are not objects. They are not required to be stored in  
    memory.  
    
- In fact, the compiler looks to optimize the code by replacing all  
    references with the object they are referencing to. There are times when  
    the compiler can’t do this, so the reference then has to be stored in  
    memory.  
    
- You can’t have a reference to a reference.