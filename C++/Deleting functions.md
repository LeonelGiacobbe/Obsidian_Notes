---
Created: 2024-02-05T23:04
---
In cases where we have a function that we explicitly do not want to  
be callable, we can define that function as deleted by using  
the   
**= delete** specifier. If the compiler matches a  
function call to a deleted function, compilation will be halted with a  
compile error.  

Example:

```C++
void doSomething(char) = delete; //calls to this func will halt programvoid doSomething(bool) = delete; //calls to this func will halt program
```