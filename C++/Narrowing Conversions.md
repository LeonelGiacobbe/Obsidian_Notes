---
Created: 2024-02-05T23:05
---
The following conversions are defined to be narrowing:

- From a floating point type to an integral type.
- From a floating point type to a narrower or lesser ranked floating  
    point type, unless the value being converted is constexpr and is in  
    range of the destination type (even if the destination type doesn’t have  
    the precision to store all the significant digits of the number).  
    
- From an integral to a floating point type, unless the value being  
    converted is constexpr and whose value can be stored exactly in the  
    destination type.  
    
- From an integral type to another integral type that cannot represent  
    all values of the original type, unless the value being converted is  
    constexpr and whose value can be stored exactly in the destination type.  
    This covers both wider to narrower integral conversions, as well as  
    integral sign conversions (signed to unsigned, or vice-versa).  
    

Because they can be unsafe and are a source of errors, avoid  
narrowing conversions whenever possible.  

In cases where narrowing conversions are unavoidable, try to use  
explicit conversions through static cast. Note that brace initialization  
disallows narrowing conversion.  

when the source type in the narrowing conversion is constexpr, this  
means that it must be known to the compiler at runtime, so the compiler  
can detect whether the transformation will work or not when  
compiling.