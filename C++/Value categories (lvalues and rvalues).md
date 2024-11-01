---
Created: 2024-02-05T23:06
---
All expressions in C++ have two properties: a type and a value category.

### The type of an expression

Refers to the type of an object, variable or function that results from an evaluated expression. The compiler uses the type of an expression to determine it its use is valid in a given context. the type  
of an expression must be determinable at compile time. The value, however, may be determined at compile time (if the expression is constexpr), or at runtime(if the expression is not constexpr).  

### The value category of an expression

The value category of an expression indicates if that expression resolves to a value, a function, or an object.

There are five possible value categories (explained later):

- lvalue  
- rvalue  

- glvalue

- prvalue

- xvalue

### Lvalue and Rvalue

An lvalue is an expression that evaluates to an identifiable object or function.

Lvalues divide into two types:

- Modifiable lvalues: can be modified (not constexpr or const)

- non-modifiable lvalues: cannot be modified (constexpr or const)

An rvalue is an expression that is not an lvalue (duh!). Common rvalues are literals and the return value of functions. Rvalues aren’t identifiable and only occur on the scope of the expression in which they exist, so they must be used immediately.

### Tip

If not sure of whether an expression is rvalue or lvalue, do:

```C++
x = 5;
&x; // compiles because var is an lvalue expression
&5; // does not compile because 5 is an rvalue expression
```

### lvalue and rvalue conversion

lvalues can implicitly convert to rvalues

### Help with identifying lvalues and rvalues

A rule of thumb to identify lvalue and rvalue expressions:

- Lvalue expressions are those that evaluate to variables or other  
    identifiable objects that persist beyond the end of the expression.  
    
- Rvalue expressions are those that evaluate to literals or values  
    returned by functions/operators that are discarded at the end of the  
    expression.