---
Created: 2024-02-05T23:04
---
- A function’s return type is not used to differentiate overloaded functions (see [[Function Overloading]]
- Functions can be differentiated based on number of parameters
- Functions can be differentiated based on type of parameters
- Type aliases (see [[Typedefs and type aliases]]) don’t work as away of differentiating functions.
    
    ```C++
    using num = int;
    add(num x, num y);
    add(int x, int y);//These two functions are not overloaded.
    ```
    
- Const qualifier is also not considered (const int == int)
- Type signature is defined as the parts of the function header that are used for differentiation. Could be name, number of parameter, type of parameter, etc.