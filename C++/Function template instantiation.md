---
Created: 2024-02-05T23:04
---
### Using a function template

To use [[Function templates]], we need to use the following  
syntax:  

```C++
someFunct<actual_type>(args); // actual_type is some actual type, like int or double
```

“actual_type” is a part of the function call named **Template Argument**

### Template argument deduction

In cases where the type of the arguments match the actual type we want, we do not need to specify the actual type – instead, we can use **template argument deduction** to have the compiler deduce the actual type that should be used from the argument types in the function call. For example, instead of making a function call like this:

```C++
std::cout << max<int>(1, 2) << '\n'; // specifying we want to call max<int>
```

We can use

```C++
std::cout << max<>(1, 2) << '\n';std::cout << max(1, 2) << '\n';// either of the two
```

### Function templates with non-template parameters

It’s possible to create [[Function templates]] that have both template parameters and non-template parameters. The type template parameters can be matched to any type, and the non-template parameters work like the parameters of normal functions. For example, in the following function definition:

```C++
template <typename T>;someFunc(T, double) {}
```

The first argument when calling someFunc can be of any type, while the second argument must be a double (or a type that can be converted / promoted to double) (see [[Numeric Promotions]] and [[Numeric conversions]])

### Using templates in multiple files

To avoid linker errors, the best practice is to put all the template  
code in a header (.h) file instead of a source (  
`.cpp`) file, then import  
that header file to wherever we want to use it.