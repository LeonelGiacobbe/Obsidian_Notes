---
Created: 2024-02-28T16:15
---
- Variable that holds a memory address as its value.
- They have a type. an `int` pointer points to a memory address of an `int` value.
- Declared by including `*` before the pointer name, like: `int* maxNum`
- The reference operator `&` obtains a variable’s address. Example: `&someVar` returns the memory address of `someVar`

```C++
int* somePointer;
int someVariable;
somePointer = &someVariable;
```

- `*` is the dereference operator.

```C++
int* somePointer = &someVariable;
cout << somePointer; // outputs memory address where someVariable is stored
cout << *somePointer; // outputs the actual value of what somePointer is pointing to
*somePointer = someOtherVariable; //changes the val of someVariable to someOtherVariable
// The statement above does not change the value of somePointer (the memory it points to)
```

  

## Null pointer

- We might wish to initialize a pointer to point to nothing by declaring it as null. We do this with `nullptr`. Example `int *somePointer = nullptr;`

  

## Allocating memory

To allocate memory for an array of a certain type:

```C++
type * varName = (type *)( new arrayType [ size ]);
```

## Pointer operators

NEW

- Allocates memory for the given type and returns a pointer to that memory
- Example: `Point *sample = new Point;`
- If the type is a class, the `new` operator also calls the constructor of that class.
- We can pass parameters to the constructor of a class while using the `new` keyword
- When using pointers, instead of calling a member function of a class by using `*pointer.func();`, we call it by `pointer->func();` **NO ASTERISK**

DELETE

- deallocates or frees a block of memory that was assigned with the `new` keyword.
- `delete pointerVariable` deletes the memory block that `pointerVariable` points to.
- The `delete[]` operator is used to delete an array that was created with the `new` kw.