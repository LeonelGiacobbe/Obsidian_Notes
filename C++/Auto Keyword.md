Most of the time, when declaring and initializing a variable at the same point, we provide redundant information to the compiler, like so:
`double d { 5.0 };`. We tell the compiler that `d` is of type double, but `5.0` is also of type `double`.
We can use the `auto` keyword to make the compiler assume the type of a variable automatically

In most cases, type deduction will drop the `const` or `constexpr` qualifier from deduced types.