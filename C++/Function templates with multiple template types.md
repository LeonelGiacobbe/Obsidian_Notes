---
Created: 2024-02-05T23:04
---
When using one template type, all parameters of a function call must  
be of the same type. For example:  

```C++
max(2, 3.5);
```

won’t work.

[[Numeric conversions]] are done only when resolving function overloads, not when performing template argument deduction.

**Possible Solutions are:**

- Use `static_cast` to convert the arguments to matching types
- Provide an explicit type template argument: basically, provide a non-template version of the function that is able to apply the implicit type conversion rules to the arguments.

### Function templates with multiple template type parameters

We can create more than one template type parameter at the same time:

```C++
template <typename T, typename U> // We're using two template type parames named T and U
auto max(T x, U y) // x can resolve to type T, and y can resolve to type U
{    
	return (x < y) ? y : x;
}
```

### Abbreviated Function Templates

When the `auto` keyword is used as a parameter type in a normal function, the compiler will automatically convert the function into a function template (see [[Function templates]]) with each auto parameter becoming an independent template type parameter. This method for creating a function template is called an **abbreviated function template**. For example:

```C++
auto max(auto x, auto y){
    return (x < y) ? y : x;
}
```

This only works if we want the type of the variables X and Y to be independent from each other. If we want them to be of the same type, we need to use the long way to define [[Function templates]].