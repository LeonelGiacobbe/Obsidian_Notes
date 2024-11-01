---
Created: 2024-02-05T23:04
---
### Containers

- A container is a data structure that provides a storage location for  
    a large number of unnamed objects (called  
    _elements_)
- The container has a name, its objects do not
- We can talk about the number of elements in a container by talking  
    about its “size” or “length”  
    
- All elements inside a container have to be of the same data  
    type.  
    

### Arrays

Array declaration: `type array_name[size];`. Ex: `int student_grades[20];`

To access a specific element of the array: `arrayName[index]`.

- An array is a container that stores its elements contiguously in  
    memory (no gaps).  
    
- In C++, there are 3 container types:
    - `C-style arrays`
    - `std::vector` container classes
    - `std:: array` container classes
- `std::vector` is the most useful and flexible of the  
    three  
    
- `std::array` can sometimes be the most efficient,  
    especially in small size arrays  
    
- The type of the array is the same as the type of its elements. All  
    elements must also be of the same type.  
    
- They are statically allocated. (See [[Static Memory allocation]])