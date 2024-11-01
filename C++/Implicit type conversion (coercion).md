---
Created: 2024-02-05T23:04
---
- Conversions do not change the value or type being converted. Instead, a new value with the desired type is created as a result of the conversion.
- If we try to do an implicit conversion and fail, then the compilation will fail with a compile error.
- Note that brace initialization (**int x { y }**) disables implicit conversion that would result in data loss.