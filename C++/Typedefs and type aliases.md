---
Created: 2024-02-05T23:05
---
**using** is a keyword that creates an alias for an existing data type.

```JavaScript
using Distance = double; // define Distance as an alias for type double
```

A type alias defined inside a block has block scope and is usable only within that block, whereas a type alias defined in the global namespace has global scope and is usable to the end of the file.

### Typedefs

A **typedef** (which is short for “type definition”) is an older way of creating an alias for a type. To create a typedef alias, we use the `typedef` keyword:

The following aliases are identical: `typedef long Miles; using Miles = long; typedef long Miles;` `using Miles = long;`

Prefer type aliases over typedefs