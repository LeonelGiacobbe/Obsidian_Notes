---
Created: 2024-02-05T23:05
---
By using the `const` keyword when declaring [[Lvalue references]], we can create a reference to a const value:

```C++
const int x { 5 };
const int& ref { x };
```

- Obviously, `lvalue` references to const can’t be modified.
- We can create a const reference to a non const variable. In that case, the reference value can’t be changed directly, but the referent can.
- Favor `lvalue` references to const over `lvalue` references to non-const.

### Initializing an `lvalue` reference to const with an `rvalue`

We can initialize `lvalue` references with `rvalues`:

```C++
const int& ref { 5 };
```

In this case, 5 is called a temporary object. Temporary objects have no scope (since they do not have an identifier), and are destroyed after the statement ends (line is changed).