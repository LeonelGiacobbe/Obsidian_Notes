---
Created: 2024-02-05T23:05
---
Lambda functions are functions without names that are designed inside another function. The syntax for them is:

```C++
[ captureClause ] ( parameters ) -> returnType
{    
	statements;
}
```

- capture close can be empty
- parameter list can be empty. It can also be skipped unless a `returnType` is defined.
- `returnType` is optional. If omitted, auto is assumed (see [[Type deduction with Auto keyword]]).

### Storing lambdas in variables

We can store lambda functions in variables and call them later. The syntax for that is:

```C++
auto myLambda = [captureClause](parameters) {    
std::cout << "Hello from lambda!" << std::endl;
};

// Calling the lambda function through the variable
myLambda();
```

### Passing lambda to function

There are three ways to do this:

- Using an `std::function` parameter
- Use [[Function templates]]
- Use abbreviated [[Function templates]]syntax

  

### Generic lambdas