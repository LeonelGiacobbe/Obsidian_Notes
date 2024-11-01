---
Created: 2024-02-05T23:04
---
- Defining 2+ functions with the same name but different parameters  
    (in type and amount)  
    
- Compiler will decide what function to use based on number and type  
    of parameters  
    

Example:

```JavaScript
int add (int x, int y){
    return (x + y);
}
double add (double x, double y){
    return (x + y)
}
```

If we call the functions with two ints, the first declaration will  
execute. If it is with two doubles, it will call the second  
function.  

``