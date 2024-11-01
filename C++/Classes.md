---
Created: 2024-02-22T15:50
---
- Might be a good idea to define a class inside a namespace:

```C++
namespace yaya {

//class definition

}
```

- Class declaration should go in header file (`nameOfClass.h`). Also forward definitions.
- Class definition should go in `nameOfClass.cpp`
- Like `self` in Python, C++ uses `this->`.

```C++
Constructor::Constructor()
{
	this-> x = 0;
}
```

  

## Destructors

```C++
~ nameOfClass();
```