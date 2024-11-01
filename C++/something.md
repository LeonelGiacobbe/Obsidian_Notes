---
Created: 2024-02-05T23:05
---
We can also use the auto keyword (see [[Type deduction with Auto  
keyword]]) to let the compiler deduce the type of the return value of a  
function.  

This is done by replacing the type in the function declaration with  
auto:  

`int add() → auto add();`

When functions using auto have multiple return statements, they all  
must have the same type.  

Forward declarations don’t work with auto.

Favor explicit return types over function return type deduction for  
normal functions.  

Type deduction (see [[Type deduction with Auto keyword]]) can’t be  
used for function parameter types