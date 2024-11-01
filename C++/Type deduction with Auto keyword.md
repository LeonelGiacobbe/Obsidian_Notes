---
Created: 2024-02-05T23:05
---
we can use the `auto` keyword to make the compiler assume the type of a variable automatically

In most cases, type deduction will drop the `const` or `constexpr` qualifier from deduced  
types.  

If using auto for strings, use the “s” prefix in the variable name. Example: `sMyString`