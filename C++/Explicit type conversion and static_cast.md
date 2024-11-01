---
Created: 2024-02-05T23:04
---
In standard C programming, casts are done via the () operator, with  
the name of the type to convert the value placed inside the  
parentheses.  

for example:

`int z = 5`

`(double) z`

However, we should prioritize static casts. The syntax is:

`static_cast<desiredType>(var)`