---
Created: 2024-02-05T23:04
---
### ARGUMENT MATCHING SEQUENCE:

1. Compiler tries to find an exact match
2. Compiler tries to find match by applying [[Numeric Promotions]] to arguments
3. Compiler tries to find a match by applying [[Numeric conversions]]
4. Compiler tries to find a match through user-defined conversions.
5. Compiler looks for a matching function that uses elipses
6. Compiler gives up and issues a compile error

### Ambiguous Matches:

Occurs when the compiler finds two or more functions that could be matched in the same step. When this occurs, compiler throws a compile error warning about the ambiguous match.

### Resolving ambiguous matches:

- define a new overloaded function (see [[Function Overloading]])
- explicitly cast the ambiguous arguments to match the type of  
    function we want to call (see  
    [[Explicit type conversion and static_cast]])

### Matching functions with multiple arguments:

If there are multiple arguments, the compiler applies the matching rules to all the arguments. The function chosen must provide a better match than all the other candidate functions for at least one parameter, and no worse for all of the other parameters.