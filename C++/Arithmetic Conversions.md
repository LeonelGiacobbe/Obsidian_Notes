---
Created: 2024-02-05T23:04
---
The compiler has a prioritized list of types that looks something  
like this:  

- `long double (highest)`
- `double`
- `float`
- `unsigned long long`
- `long long`
- `unsigned long`
- `long`
- `unsigned int`
- `int (lowest)`

There are only two rules:

- If the type of at least one of the operands is on the priority list,  
    the operand with lower priority is converted to the type of the operand  
    with higher priority.  
    
- Otherwise (the type of neither operand is on the list), both  
    operands are numerically promoted