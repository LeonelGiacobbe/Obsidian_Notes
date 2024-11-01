---
Created: 2024-02-05T23:04
---
- signed char or signed short can be converted to int.
- unsigned char, char8_t, and unsigned short can be converted to int if int can hold the entire range of the type, or unsigned int otherwise.
- If char is signed by default, it follows the signed char conversion rules above. If it is unsigned by default, it follows the unsigned char conversion rules above.
- bool can be converted to int, with false becoming 0 and true becoming 1.

The above basically means that `bool`, `char`, `signed char`, `unsigned char`, `signed short`, and `unsigned short` all get promoted to `int`.